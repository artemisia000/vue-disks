<template>
<div class="body">
  <section class="container text-center" >
    
        <div v-if="version !== null" class="row justify-content-center">

            <div class="col-6 col-md-4 col-lg-1 m-4"
                 v-for="(card, index) in version"
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

import Card from '@/components/Card.vue';



export default {
    name: 'CardList',

    components: {
        Card,
    },

    props: {
        version: Array
    },  

};


</script>

<style  scoped lang="scss">

.body{
    background-color: #1d2d3c;
    width: 100%;
    height: 100vh;
}




</style>