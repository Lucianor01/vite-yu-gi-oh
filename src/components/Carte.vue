<script>

export default {
    name: "Carte",
    props: ['carteYuGiOh'],
    data() {
        return {

        }
    },
    methods: {

    },
}

</script>

<template>
    <div class="card col-12 col-md-5 col-lg-2 p-0">
        <img :src="carteYuGiOh.card_images[0].image_url" class="card-img-top" :alt="carteYuGiOh.name">
        <div class="card-body text-center">
            <h5 class="card-title text-light">{{ carteYuGiOh.name }}</h5>
            <span class="card-text">
                {{ carteYuGiOh.archetype == null ? 'undefined' : carteYuGiOh.archetype }}
            </span>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card {

    .card-body {
        background-color: hsl(33, 64%, 53%);
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
    }
}
</style>
