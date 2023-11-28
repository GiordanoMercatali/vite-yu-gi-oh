<script>

import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import {store} from "./store.js";
import CardsList from "./components/CardsList.vue";
import AppSearch from "./components/AppSearch.vue";

export default {
  data() {
    return {
      store
    }
  },
  created() {
    this.store.loading = true;
    this.getCards();
  },
  components: {
    AppHeader,
    CardsList,
    AppSearch,
  },
  methods: {
    getCards(){
        axios.get(this.store.apiUrl).then((resp) => {
        this.store.cardsArray = resp.data.data;
        this.store.loading = false;
      });
    },

    searchArchetype() {
      console.log(this.store.searchText);
      axios.get(this.store.apiUrl, {
          params: {
            archetype: this.store.searchText,
          },
        }).then((resp) => {
          this.store.cardsArray = resp.data.data;
        });
    },
  },
};

</script>

<template>

  <AppHeader />
  <AppSearch @performSearch="searchArchetype" />
  <CardsList />

</template>

<style lang="scss">

  @use "./style/general.scss";

</style>
