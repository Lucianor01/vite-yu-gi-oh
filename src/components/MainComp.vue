<script>
import { store } from '../store';
import Carte from './Carte.vue'
import SelectCarte from './SelectCarte.vue'

export default {
    name: "MainComp",
    components: {
        Carte,
        SelectCarte
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
        <SelectCarte />
        <div class="container p-5" id="container-cards">
            <div class="bg-dark p-3">
                <span class="text-light">Found {{ store.arrayCarte.length }} cards</span>
            </div>
            <div class="container">
                <div class="row justify-content-between gap-4">
                    <Carte v-for="(carte, index) in store.arrayCarte" :key="index" :carteYuGiOh="carte" />
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
#container-cards {
    background-color: white;
}
</style>
