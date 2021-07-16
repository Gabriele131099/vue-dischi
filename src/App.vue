<template>
  <div id="app">
        <Header @select="searchGenre" :tmpGenre="tmpGenre"/>
        <Main :albums="getFilterAlbumGenre"
        :inputSelectGenre="inputSelectGenre"/>
        <Cards v-if="albums.length === 0"/>

  </div>
</template>

<script>
import Header from "./components/Header.vue";
import axios from 'axios';
import Cards from './components/Cards.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Cards
  },
  data:function(){
    return {
      albums: [],
      inputSelectGenre: "",
      tmpGenre:[],

     }

     
  },
  created() { //facciamo la nostra chiamata Api
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.albums = result.data.response //(element).data.(array che ci serve)
      this.searchGenre('')
      this.filterSelect('')
       
    });
  },
  computed:{
    getFilterAlbumGenre(){
      return this.albums.filter((album)=> {
        if (this.inputSelectGenre === 'All') {
          return true
        }
        return album.genre.includes(this.inputSelectGenre)
      })
    }
  },
    methods:{
      filterSelect: function(){
        let arrayGenre=[]
        for (let i = 0; i < this.albums.length; i++) {
          let album = this.albums[i]
          if (!arrayGenre.includes(album.genre)) {
            arrayGenre.push(album.genre)
          } 
          
        }
        this.tmpGenre= arrayGenre
      },
      searchGenre: function(selectGenre){
        this.inputSelectGenre = selectGenre 
      }
    }

  }



</script>

