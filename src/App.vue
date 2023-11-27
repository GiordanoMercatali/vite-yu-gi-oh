<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import {store} from "./store.js";
import CardsList from "./components/CardsList.vue";

export default {
  data() {
    return {
      store
    }
  },
  created() {
    axios.get(this.store.apiUrl).then((resp) => {
      this.store.cardsArray = resp.data;
    })
  },
  components: {
    AppHeader,
    CardsList,
  },
};

</script>

<template>

  <AppHeader />

  <AppContent />

  <AppFooter />

</template>

<style lang="scss">

  /*@use "./style/general.scss";*/

</style>
