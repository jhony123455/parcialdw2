<template>
  <div>
        <header class="encabezado">
            <nav class="menu">
              <li>EMISORAS</li>
              <li>PODCASTS</li>
              <li>MI LISTA</li>
              <li>BUSQUEDA</li>
            </nav>
        </header>
    </div>
</template>

<script>
export default {
 name:'HeaderComp'
}
</script>

<style scoped>

.encabezado{
    height: 80px;
    background: #455A64;
    display: flex;
    justify-content: space-around;
    color: #fff;
}
.menu{
    display: flex;
    justify-content: space-around;
    align-items: center;
    gap: 13rem;
}

.menu li{
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 1rem;
}

.menu li:hover{
    border-bottom: solid #fff 3px;
}
</style>