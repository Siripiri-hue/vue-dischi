<template>
    <div class="card">
        <figure class="poster">
            <img :src="disc.poster">
        </figure>
        
        <div class="info">
            <p class="title">{{ disc.title }}</p>
            <p class="author">{{ disc.author }}</p>
            <p class="year">{{ disc.year }}</p>
            <!-- <p class="year">{{ disc.genre }}</p> -->
        </div>
    </div>
</template>

<script>
export default { 
    props: {
        disc: {
            type: Object,
            required: true,
        },
    },    
}
</script>

<style lang="scss" scoped>

.card {
    background-color: #2E3A46;
    color: white;
    text-align: center;
    max-width: calc((100% - 40px) / 5);
    // flex-grow: 1;
    padding: 5px;

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