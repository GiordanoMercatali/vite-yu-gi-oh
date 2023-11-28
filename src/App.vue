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
    this.getCards();
    // axios.get(this.store.apiUrl).then((resp) => {
    //   this.store.cardsArray = resp.data.data;
    //   this.store.loading = false;
    // })
  },
  components: {
    AppHeader,
    CardsList,
  },
  methods: {
    getCards(){
        axios.get(this.store.apiUrl).then((resp) => {
        this.store.cardsArray = resp.data.data;
        this.store.loading = false;
      });
    }
  },
};

</script>

<template>

  <AppHeader />
  <CardsList />

</template>

<style lang="scss">

  @use "./style/general.scss";

</style>
