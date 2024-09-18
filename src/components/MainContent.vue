<template>
   <div>
    <main class="main-content">
      <section class="emisoras-image">
        <div class="emisora" v-for="emisora in emisoras" :key="emisora.id" >
          {{ emisora.imagen}}
          <img :src="emisora.imagen" alt="">
        </div>
      </section>
      <section class="list-emisoras">
        <ul>
          <li v-for="genero in generos" :key="genero.id" class="genero-item">
            {{ genero.nombre }}
          </li>
        </ul>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      emisoras: [],
      generos: [],
    };
  },
  created() {
    this.getAllEmisoras();
    this.getAllGeneros();
  },
  methods: {
    async getAllEmisoras() {
      const apiUrl = 'https://cobuses.com.co/APIV2/model/radio.php?dato=getallemisoras';
      try {
        const response = await this.axios.get(apiUrl);
        this.emisoras = response.data;
        console.log(response.data);
      } catch (error) {
        console.error('Error al obtener emisoras:', error);
      }
    },
    async getAllGeneros() {
      const apiUrl = 'https://cobuses.com.co/APIV2/model/radio.php?dato=getallgeneros';
      try {
        const response = await this.axios.get(apiUrl);
        this.generos = response.data;
        console.log(response.data);
      } catch (error) {
        console.error('Error al obtener géneros:', error);
      }
    },
  },
};
</script>

<style>
.main-content {
  display: flex;
  width: 100%;
  height: auto;
  background-color: #455A64;
  
}

.emisoras-image{
  width: 70%;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  gap: 5px;
  padding: 10px;
  background-color: #21404B;
  border-right: solid #fff 1px;

}

.emisora{
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
  width: 100px;
  height: 100px; 
 

}


.emisora img{
  width: 100%;
  height: 100%;
  object-fit: cover;
}


.list-emisoras{
  width: 30%;
  background-color: #21404B;
  padding: 10px;
}

.genero-item{
  background-color:  #455A64;
  color: #fff;
  padding: 10px;
  margin-bottom: 5px;
  list-style: none;
  cursor: pointer;
}

.genero-item:hover{
  background-color: #697A82;
}

</style>