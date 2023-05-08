<script>

import { store } from './store';
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';

export default {
  name: "App",
  components: {
    HeaderComp,
    MainComp,
  },
  data() {
    return {
      store
    }
  },
  created() {
    // this.apiCarte
    //this.archetypesApi
  },
  computed: {
    // apiCarte() {
    //   axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=0')
    //     .then((res) => {
    //       console.log(res.data.data)

    //       const datiApi = res.data.data

    //       this.store.arrayCarte = datiApi
    //     })
    // },

  },
}
</script>

<template>
  <HeaderComp />
  <main>
    <MainComp />
  </main>
</template>

<style lang="scss">
@use './style/main.scss'
</style>
