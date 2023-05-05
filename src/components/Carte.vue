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
    <div class="card col-2" style="width: 18rem;">
        <img :src="carteYuGiOh.card_images[0].image_url" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ carteYuGiOh.name }}</h5>
            <p class="card-text"></p>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>
