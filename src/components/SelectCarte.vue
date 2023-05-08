<script>
import { store } from '../store';
import axios from 'axios';
export default {
    name: "SelectCarte",
    data() {
        return {
            store
        }
    }, methods: {
        archetypesApi() {
            axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${this.store.arraySelect}`)
                .then((res) => {
                    console.log(res.data.data)

                    const datiApi = res.data.data

                    this.store.arraySelect = datiApi
                })
        }
    }
}

</script>

<template>
    <div class="container mb-4">
        <select class="form-select" aria-label="Default select example" v-model="store.arraySelect"
            @click.prevent="archetypesApi">
            <option selected>Alien</option>
            <option value="Albaz_Dragon">Albaz Dragon</option>
            <option value="Grepher">Grepher</option>
            <option value="Train">Train</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
.form-select {
    width: 120px;
}
</style>
