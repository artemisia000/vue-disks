<template>
  <div id="app" >

    <Header />

  

    <CardList />




  </div>



</template>

<script>
import Header from '@/components/Header.vue';
import CardList from '@/components/CardList.vue';


export default {
  name: 'App',
  components: {
    Header,
    CardList,
 
  }
}


</script>

<style lang="scss">
@import '@/styles/globals';

*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Cabin', sans-serif;
  font-family: 'Cabin Sketch', cursive;
  font-family: 'Outfit', sans-serif;
  
}



</style>
