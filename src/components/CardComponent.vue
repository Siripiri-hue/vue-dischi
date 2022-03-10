<template>
    <div class="card">
        <figure>
            <img src="../assets/logo.png" alt="">
        </figure>
        
        <div class="info">
            <p class="title">Blabla</p>
            <p class="author">Blabla</p>
            <p class="year">Blabla</p>
        </div>
    </div>
</template>

<script>
export default {

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
        }

        .author, .year {
            color: #50585E;
        }
    }
}

</style>