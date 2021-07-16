<template>
    <div>
        <nav class="nav-first">
            <img src="@/assets/spotify-logo.png" alt="">
        <div class="container-genre">

            <select class="genre" placeholder="All" 
            v-model="selectGenre">
                <option value="All">All</option>
                <option v-for="(genre , index) in tmpGenre"
                :key="index"
                :value="genre">
                {{genre}}
                </option>all

            </select> 

            <button @click="$emit('select',selectGenre)">Filtra</button>


        </div>
        </nav>
    </div>
</template>
<script>
export default {
  name:'Header',
  props:{
      tmpGenre: Array
  },
  data(){
      return {
          selectGenre:"",

      }
  },
  
}
</script>
<style lang="scss">
    .container-genre{
        margin: 15px;
            button{
                padding: 5px 10px;
                border-radius: 15px;
                background-color: rgba(38, 129, 73, 0.5);
                color: whitesmoke;
                border: 1px solid rgb(22, 22, 71);
            }
    }
    .genre{
        background-color: rgb(245, 244, 244);
        border-radius: 10px;
        margin: 15px;
        padding: 5px ;
        outline: none;
    }
 
  
  .nav-first
  {
      background-color: rgb(17, 34, 49) ;
      display: flex;
      align-items: center;
      justify-content: space-between;
    img {
        width: 100px;
        padding: 15px;
    }
}

</style>
