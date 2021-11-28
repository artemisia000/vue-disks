<template>
  <div id="app" >

    <Header  @search="searchDisk" />

    <CardList :version="lista"/>

  </div>

</template>

<script>
import Header from '@/components/Header.vue';
import CardList from '@/components/CardList.vue';
import axios from 'axios';


export default {
  name: 'App',
  components: {
    Header,
    CardList,
  },
   data(){
        return{
            lista: null,
           searchGenre: '',
        };
    },
    created(){
        this.getCard();
    },
    methods: {
        getCard() {

            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                  .then(result =>  {
                      console.log(result.data.response);
                      this.lista = result.data.response;
                  })
                  .catch(error => console.log(error));
           },

           searchDisk(word){
             console.log(word);
             this.searchGenre = word;
           }
     },
};

</script>

<style lang="scss">
@import '@/styles/globals';

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Cabin', sans-serif;
  font-family: 'Cabin Sketch', cursive;
  font-family: 'Outfit', sans-serif; 
}


</style>