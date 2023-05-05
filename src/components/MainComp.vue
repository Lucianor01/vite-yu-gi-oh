<script>
import { store } from '../store';
import Carte from './Carte.vue'

export default {
    name: "MainComp",
    components: {
        Carte
    },
    data() {
        return {
            store
        }
    },
    methods: {

    },
}

</script>

<template>
    <div class="container-fluid p-4">
        <div class="container mb-4">
            <select class="form-select" aria-label="Default select example">
                <option selected>Alien</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>
        </div>
        <div class="container p-5" id="container-cards">
            <div class="bg-dark p-3">
                <span class="text-light">Found {{ store.arrayCarte.length }} cards</span>
            </div>
            <div class="container">
                <div class="row justify-content-between gap-5">
                    <Carte v-for="(carte, index) in store.arrayCarte" :key="index" :carteYuGiOh="carte" />
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.form-select {
    width: 120px;
}

#container-cards {
    background-color: white;
}
</style>
