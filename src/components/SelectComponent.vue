<template>
    <div id="genre-select">
        <label for="cars">Choose a genre: </label>
        <select name="genres" id="genres" v-model="value" @change="filterGenre(value)">
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
            value: "",
        }
    },

    methods: {
        filterGenre: function(genre) {
            this.$emit("selectGenre", genre);
            this.value = genre;
            console.log(genre);
        }
    }
}
</script>

<style lang="scss" scoped>

</style>