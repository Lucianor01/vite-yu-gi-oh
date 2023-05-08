<script>
import { store } from '../store';
import axios from 'axios';
import LoaderComp from './LoaderComp.vue'

export default {
    name: "SelectCarte",
    components: {
        LoaderComp
    },
    data() {
        return {
            store
        }
    },
    created() {
        this.archetypesApi
    },
    computed: {
        archetypesApi() {

            store.loadingData = true

            if (store.arraySelect !== '') {

                axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.arraySelect}`)
                    .then((res) => {
                        // console.log(res.data.data)

                        store.loadingData = false

                        const datiApi = res.data.data

                        store.arrayCarte = datiApi
                    })
            } else {
                axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=0`)
                    .then((res) => {
                        // console.log(res.data.data)

                        store.loadingData = false

                        const datiApi = res.data.data

                        store.arrayCarte = datiApi
                    })
            }
        }
    }
}

</script>

<template>
    <LoaderComp v-if="store.loadingData" />
    <div class="container mb-4">
        <select class="form-select" aria-label="Default select example" v-model="store.arraySelect" @click="archetypesApi">
            <option disabled value="">Please select one</option>
            <option value="Alien">Alien</option>
            <option value="Exodia">Exodia</option>
            <option value="Libromancer">Libromancer</option>
            <option value="Train">Train</option>
            <option value="Dark Magician">Dark Magician</option>
            <option value="Cyber Dragon">Cyber Dragon</option>
            <option value="Elemental HERO">Elemental HERO</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
.form-select {
    width: 200px;
}
</style>
