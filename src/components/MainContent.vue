<template>
    <main>
        <Select />

        <section id="grid">
            <Card v-for="(disc, index) in discs" :key="index" 
            :src="disc.poster" :title="disc.title" :author="disc.author" :year="disc.year" />
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
    // height: calc(100vh - 10vh);
    // flex-grow: 1;
    background-color: #1E2D3B;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    color: white;
    padding-top: 20px;

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