<template>
    <main>
        <section id="grid">
            <Card v-for="(disc, index) in discs" :key="index" 
            :src="disc.poster" :title="disc.title" :author="disc.author" :year="disc.year" />
        </section>
    </main>
</template>

<script>
import Card from './CardComponent.vue'
import axios from 'axios'

export default {
    data() {
        return {
            discs: []
        }
    },

    methods: {
        apiCalling() {

            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
                .then ( res => {
                    this.discs = res.data.response;
                    console.log(res.data.response);
                })
                .catch ( err => {
                    console.log(err);
                })
        }
    },

    components: {
        Card,
    },

    created() {
        this.apiCalling();
    }
}
</script>

<style lang="scss" scoped>

main {
    height: calc(100vh - 10vh);
    background-color: #1E2D3B;
    // flex-grow: 1;

    #grid {
        width: 1024px;
        margin: 0 auto;
        padding: 20px 0;
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
    }
}

</style>