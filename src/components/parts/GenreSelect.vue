<template>
  <div>
      <select name="genreSelect" @change="saveGenre">
        <option value="default">-</option>
        <option value="Rock">Rock</option>
        <option value="Metal">Metal</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
      </select>
  </div>
</template>

<script>
export default {
name: "GenreSelect",
data(){
    return{
        selectedGenre: "",
    }
},
methods: {
    saveGenre: function (e) {
        
        this.selectedGenre = e.target.value;
        this.$emit('selectedValue', this.selectedGenre)
    }
}

}
</script>

<style>

</style>