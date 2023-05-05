<script>
import Carte from './Carte.vue'

export default {
    name: "MainComp",
    components: {
        Carte
    },
    data() {
        return {

        }
    },
    methods: {

    },
}

</script>

<template>
    <div class="container p-4">
        <select class="form-select" aria-label="Default select example">
            <option selected>Alien</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
        </select>
        <div>

        </div>
    </div>
</template>

<style lang="scss" scoped>
.form-select {
    width: 120px;
}
</style>
