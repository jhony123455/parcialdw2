<template>
 <div>
  <HeaderComp></HeaderComp>
  <MainContent></MainContent>
  <FooterComp></FooterComp>
 </div>
</template>

<script>
import MainContent from '@/components/MainContent.vue';
import FooterComp from '@/components/FooterComponent.vue';
import HeaderComp from '@/components/HeaderComponent.vue';
export default {

components:{FooterComp,HeaderComp,MainContent},
 name: 'PruebaView',

        
}
</script>

<style>

</style>