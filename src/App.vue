<template>
  <div id="app">
        <Header/>
        <Main :albums="albums"/>

  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from 'axios'
export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return
     {
       albums:[]
     }
    
  },
  created() { //facciamo la nostra chiamata Api
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.albums = result.data.response //(element).data.(array che ci serve)
    })
  },

}



</script>

