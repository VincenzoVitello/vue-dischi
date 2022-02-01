<template>
  <div class="ms_container">
    <div v-if="loading" class="loader">Loading...</div>
    <div v-else>
      <div v-for="(card, index) in filteredArray" :key="index" class="card">
        <Cards :album="card"/>
      </div>
       <GenreSelect @selectedValue="genreFilter"/>
    </div>
    
    
  </div>
</template>

<script>

import Cards from './parts/Cards.vue'
import GenreSelect from './parts/GenreSelect.vue'
import axios from "axios";

export default {
name: 'MainSection',
created(){
    this.getCards();
}, 
computed: {
  filteredArray(){
    console.log(this.songsArray.filter (album => album.genre.toLowerCase() == this.musicGenre.toLowerCase() ));
    return this.songsArray.filter (album => album.genre.toLowerCase() == this.musicGenre.toLowerCase() );

  }
},
methods: {

    getCards(){
      axios
      .get(this.APIurl)
      .then( (risposta) => {
          this.songsArray = risposta.data.response;
          console.log(risposta.data.response)
          console.log(this.songsArray)
          this.loading = false;
        })
      .catch(function (error) {
                  // handle error
          console.log(error);
      });
    }, //chiusura getCards

    genreFilter: function(selectedGenre){
      this.musicGenre = selectedGenre;
   } //chiusura genreFilter
 },//chiusura methods
data() {
    return {
        APIurl: 'https://flynn.boolean.careers/exercises/api/array/music',
        songsArray: [],
        loading: true,
        musicGenre: ""
    }
}, //chiusura data
 components: {
   Cards,
   GenreSelect
 }, //chiusura Components

} //chiusura Export
</script>

<style lang="scss">
@import '../assets/main.scss';
</style>