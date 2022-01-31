<template>
  <div>
      <section class="ms_header_logo">
          <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/spotify-download-logo-30.png" alt="">
      </section>
  </div>
</template>

<script>
export default {
 name: 'Header',
}
</script>

<style lang="scss">
@import '../assets/vars.scss';
    .ms_header_logo{
        width: 100vw;
        height: 60px;
        background-color: $mainColor;
        display: flex;
        align-items: center;
        img{
            max-height: 50px;
            margin-left: 20px;
        }
    }

</style>