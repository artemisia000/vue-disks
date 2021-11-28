<template>
<div class="body">
  <section class="container text-center" >
    
        <div v-if="lista !== null" class="row justify-content-center">

            <div class="col-6 col-md-4 col-lg-1 m-4 "
                 v-for="(card, index) in lista"
                 :key="`card-${index}`"            
            >   
                   <Card            
                      :image= "card.poster"
                      :album= "card.title"
                      :artist= "card.author"
                      :date= "card.year"
                      :gen= "card.genre"
                   />
            </div>
        </div>
        <div v-else>Loading</div>
        
  </section>
</div>

</template>

<script>
import axios from 'axios';
import Card from '@/components/Card.vue';



export default {
    name: 'CardList',

    components: {
        Card,
    },
    
    data(){
        return{
            lista: null,
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

        }
    }

}


</script>

<style  scoped lang="scss">

.body{
    background-color: #1d2d3c;
    width: 100%;
    height: 100vh;
}




</style>