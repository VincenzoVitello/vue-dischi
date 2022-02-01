<template>
  <div class="ms_container">
    <div  v-if="loading" class="loader">Loading...</div>
    <div v-for="(card, index) in songsArray" :key="index" class="card" v-else>
      <Cards :album="card"/>
    </div>
    
  </div>
</template>

<script>

import Cards from './parts/Cards.vue'
import axios from "axios";

export default {
name: 'MainSection',
created(){
    this.getCards();
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
     }
 },
data() {
    return {
        APIurl: 'https://flynn.boolean.careers/exercises/api/array/music',
        songsArray: [],
        loading: true,

    }
},
 components: {
   Cards
 }, //chiusura Components

} //chiusura Export
</script>

<style lang="scss">
@import '../assets/main.scss';
</style>