<template>
   <div class="disk">

        <img :src="image" alt="">
        <h3>{{  album }}]</h3>
        <h4>{{  artist }}</h4>
        <p>{{ date }}</p>
        <p>{{  gen }}</p> 


   </div>


</template>

<script>
export default {
    name: 'Card',
    props: {
        image: String,
        album: String,
        artist: String,
        date: String,
        gen: String,
    },

};
</script>



<style  scoped lang="scss">



</style>