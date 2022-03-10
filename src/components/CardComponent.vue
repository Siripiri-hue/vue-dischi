<template>
    <div class="card">
        <figure class="poster">
            <img :src="src">
        </figure>
        
        <div class="info">
            <p class="title">{{ title }}</p>
            <p class="author">{{ author }}</p>
            <p class="year">{{ year }}</p>
        </div>
    </div>
</template>

<script>
export default { 
    props: {
        src: String,
        title: String,
        author: String,
        year: String,
    }
}
</script>

<style lang="scss" scoped>

.card {
    background-color: #2E3A46;
    color: white;
    text-align: center;
    width: calc(95% / 5);
    flex-grow: 1;

    .info {

        .title {
            text-transform: uppercase;
            font-weight: 700;
            padding: 10px 0;
        }

        .author, .year {
            color: #50585E;
        }
    }
}

</style>