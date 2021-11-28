<template>
   <div class="disk">

        <img :src="image" alt="">
        <h3>{{  album }}</h3>
        <h4>{{  artist }}</h4>
        <p>{{  gen }}</p>
        <p>{{ date }}</p>


   </div>


</template>

<script>
export default {
    name: 'Card',
    props: {
        image: String,
        album: String,
        artist: String,
        gen: String,
        date: String,
    },

};
</script>



<style  scoped lang="scss">

.disk{
    width: 120px;
    height: 270px;
    background-color: #2e3a46;
    color: #73777c;
    text-align: center;

    img{
        width: 100px;
        height: 100px;
        margin-top: 10px;
    }

    h3{
        font-size: 15px;
        text-transform: uppercase;
        color: #fff;
        margin-top:20px;
       
    }

    h4{
        font-size: 14px;
        margin-top: 8px;
         margin-bottom: 2px;
    }

    p{
        font-size: 12px;
        margin-bottom: 2px;
    }

    p:last-child{
        color: #fff;
    }
}



</style>