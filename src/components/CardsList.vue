<template>
    <div class="container">
        <AppLoader v-if="store.loading" />
        <div class="row" v-else>
            <div class="col" v-for="card in store.cardsArray" :key="card.id">
                <AppCard :card="card" />
            </div>
        </div>
    </div>
</template>

<script>
import {store} from "../store";
import AppCard from "./AppCard.vue";
import AppLoader from "./AppLoader.vue";

export default {
    data() {
        return {
            store,
        };
    },
    components: {AppCard, AppLoader},
}
</script>

<style lang="scss" scoped>
    
</style>