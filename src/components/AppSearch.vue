<template>
    <div>
      <select id="archetypes" name="archetype-list" class="form-control" v-model="store.searchText"> 
            <option value="" selected="selected">--Choose an archetype--</option>
            <option value="alien">Alien</option>
            <option value="Ally of Justice">Ally of Justice</option>
            <option value="Ancient Gear">Ancient Gear</option>
        </select>
      <button @click="$emit('performSearch')" class="btn btn-primary">Search</button>
    </div>
</template>

<script>
import {store} from "../store";
export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<style lang="scss" scoped>
    
</style>