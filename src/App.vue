<template>
  <div id="app">
        <Header/>
        <Main :albums="albums"/>

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
    albums: []
     }
    
  },
  created() { //facciamo la nostra chiamata Api
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.albums = result.data.response //(element).data.(array che ci serve)
    })
  },

}



</script>

