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
    this.store.loading = true;
    axios.get(this.store.apiUrl).then((resp) => {
      this.store.cardsArray = resp.data;
      this.store.loading = false;
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
