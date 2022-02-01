<template>
  <div>
      <section class="ms_header_logo">
        <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/spotify-download-logo-30.png" alt="">
        <GenreSelect/>
      </section>

  </div>
</template>

<script>
import GenreSelect from "./parts/GenreSelect.vue"
export default {
 name: 'Header',
 components:{
GenreSelect
 } 
}
</script>

<style lang="scss">
@import '../assets/vars.scss';
    .ms_header_logo{
        width: 100vw;
        height: 60px;
        background-color: $mainColor;
        display: flex;
        justify-content: space-between;
        align-items: center;
        select{
          width: 100px;
          text-align: center;
          height: 30px;
          outline: none;
          margin-right: 20px;
        }
        img{
            max-height: 50px;
            margin-left: 20px;
        }
    }

</style>