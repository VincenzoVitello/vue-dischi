<template>
  <div>
      <img :src="album.poster" alt="">
      <h4>{{album.author}}}</h4>
      <p>{{album.title}}</p>
      <p>{{album.year}}</p>
  </div>
</template>

<script>

export default {
 name: 'Cards',
 props: {
     album: Object
 }
}


</script>

<style lang='scss'>
@import '../../assets/vars.scss';

    .card{
    background-color: $mainColor;
    height: 300px;
    max-width: 190px;
    text-align: center;
    color: white;
    padding: 20px;
    margin: 10px;
    img{
        max-width: 150px;
        object-fit: contain;
        margin-bottom: 30px;
    }
    h4{
        margin-bottom: 15px;
        text-transform: uppercase;
        font-weight: bold;
    }
    p{
        color: $fontColor;
    }

}
</style>