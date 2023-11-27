<template>
    <div class="container">
        
        <div class="row">
            <div class="col">

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
    components: {AppCard},
}
</script>

<style lang="scss" scoped>
    
</style>