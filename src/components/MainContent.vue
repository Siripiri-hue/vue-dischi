<template>
    <main>
        <Select @select-genre="filterAlbum" />

        <section id="grid">

            <!-- :src="disc.poster" :title="disc.title" :author="disc.author" :year="disc.year"  -->
            <Card v-for="(element, index) in filteredGenre" :key="index" 
            :disc="element" />
        </section>
    </main>
</template>

<script>
import Card from './CardComponent.vue'
import axios from 'axios'
import Select from './SelectComponent.vue'

export default {
    data() {
        return {
            albums: [],
            selectedGenre: "",
        }
    },

    computed: {
        filteredGenre: function() {
            return this.albums.filter((element) => {
                const {genre} = element;
                return genre.toLowerCase().includes (this.selectedGenre.toLowerCase());
            })
        }
    },

    methods: {
        apiCalling() {

            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
                .then ( res => {
                    this.albums = res.data.response;
                    console.log(res.data.response);
                })
                .catch ( err => {
                    console.log(err);
                })
        }, 

        filterAlbum(genre) {
            this.selectedGenre = genre;
            console.log(genre);
        }
    },

    components: {
        Select,
        Card,
    },

    created() {
        this.apiCalling();
    }
}
</script>

<style lang="scss" scoped>


main {
    height: calc(100vh - 8vh);
    // flex-grow: 1;
    background-color: #1E2D3B;
    display: flex;
    flex-direction: column;
    align-items: center;
    color: white;
    padding-top: 20px;
    overflow: hidden;

    #grid {
        width: 1024px;
        margin: 0 auto;
        padding: 20px 0;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 10px;
    }
}



</style>