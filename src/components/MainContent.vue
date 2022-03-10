<template>
    <main>
        <section id="grid">
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
        </section>
    </main>
</template>

<script>
import Card from './CardComponent.vue'

export default {
    components: {
        Card,
    }
}
</script>

<style lang="scss" scoped>

main {
    height: calc(100vh - 10vh);
    background-color: #1E2D3B;
    flex-grow: 1;
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