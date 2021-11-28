<template>
<header>
    <div class="logo"></div>

    <form class="d-flex">
        <input class="control" 
               type="text"
               placeholder="Chose the genre"
               v-model.trim="searchGenre"
        />

        <button
             type="submit"
             class="btn"
             @click="$emit('search', searchGenre)"
         
        >
        Search
        </button>
    </form>
</header>
  
</template>

<script>
export default {
    name: 'Header',

    props: {
        word: String
    },
   data() {
       return{
           searchGenre: '',
       }
   }
}

</script>

<style scoped lang="scss" >

  header{
      height: 70px;
      background: #2e3a46;
      display: flex;
      align-items: center;

      .btn{
          border: 2px solid #1ed760;
          color: #fff;
      }

      .control{
          border-radius: 5px;
          margin: 0 10px;
      }
    
       .logo{
      width: 50px;
      height: 50px;
      background-image: url(../assets/logo.png);
      background-size: cover;
      margin: auto 10px;
      
      img{
          background-color: #2e3a46;
      }



  }

 
     
  }



</style>