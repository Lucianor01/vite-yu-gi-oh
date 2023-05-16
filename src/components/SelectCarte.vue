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
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((res) => {
                // console.log(res.data)

                store.arrayArchetype = res.data

            })
        this.archetypesApi
    },
    computed: {
        archetypesApi() {

            store.loadingData = true

            if (store.inputSelect !== '') {

                axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.inputSelect}`)
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
        <select class="form-select" aria-label="Default select example" v-model="store.inputSelect" @click="archetypesApi">
            <option disabled value="">Please select one</option>
            <option :value="elem.archetype_name" v-for="(elem, index) in store.arrayArchetype" :key="index">
                {{ elem.archetype_name }}</option>

        </select>
    </div>
</template>

<style lang="scss" scoped>
.form-select {
    width: 200px;
}
</style>
