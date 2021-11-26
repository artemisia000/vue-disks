<template>

  <section class="container" >
    
          <div v-if="response === 0" class="row">

              <div v-for="card in response"
                  :key="`card-${card.index}`"
                  class="poster"
              >

              <img :src="card.poster" alt="">
              <h3>{{  card.title }}]</h3>
              <h4>{{  card.author }}</h4>
              <p></p>
                 
              </div>
              
          </div>
          <div v-else>Loading</div>
        
  </section>


</template>

<script>
import axios from 'axios';



export default {
    name: 'CardList',
    data(){
        return{
            response: [],
        };
    },
    created(){
        this.getCard();
    },
    methods: {
        getCard() {

            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                  .then(result =>  {
                      console.log(result.data);
                      this.response = result.data;
                  })


        }
    }

}


</script>

<style  scoped lang="scss">

.poster{
    width: 60px;
    height: 200px;
}
  

</style>