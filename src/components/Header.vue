<template>
    <div>
        <nav class="nav-first">
            <img src="@/assets/spotify-logo.png" alt="">
        </nav>
        <div>

            <select class="genre" 
            v-model="selectGenre">
                <option value="All">All</option>
                <option v-for="(genre , index) in tmpGenre"
                :key="index"
                :value="{genre}">
                {{genre}}
                </option>all

            </select> 

            <button @click="$emit('select',selectGenre)">Filtra</button>


        </div>
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

  
  .nav-first
  {
      background-color: rgb(17, 34, 49) ;
    img {
        width: 100px;
        padding: 15px;
    }
}

</style>
