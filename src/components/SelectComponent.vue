<template>
    <div id="genre-select">
        <label for="cars">Choose a genre: </label>
        <select name="genres" id="genres" v-model="genreFromSelect" @change="$emit('select-genre', genreFromSelect)">
            <option value="" disabled selected>Select your option</option>
            <option value="rock">Rock</option>
            <option value="jazz">Jazz</option>
            <option value="pop">Pop</option>
            <option value="rap">Rap</option>
        </select>
    </div>
</template>

<script>
export default {
    data() {
        return {
            genreFromSelect: "",
        }
    },

    methods: {
        // filterGenre: function(genre) {
        //     this.value = genre;
        //     console.log(genre);
        // }
    }
}
</script>

<style lang="scss" scoped>

</style>