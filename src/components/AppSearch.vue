<template>
    <div>
      <select id="archetypes" name="archetype-list" class="form-control" v-model="store.searchText"> 
            <option value="" selected="selected">--Choose an archetype--</option>
            <!-- <option value="alien">Alien</option>
            <option value="Ally of Justice">Ally of Justice</option>
            <option value="Ancient Gear">Ancient Gear</option> -->
            <option v-for="(archetype, index) in archetypes" :key="index" :value="archetype">{{ archetype }}</option>
        </select>
      <button @click="$emit('performSearch')" class="btn btn-primary">Search</button>
    </div>
</template>

<script>
import {store} from "../store";
export default {
  emits: ["performSearch"],
  data() {
    return {
      store,
      archetypes: [ //Use 'v-for' and an array to declare the 'options' instead of doing it manually
        "Alien",
        "Ally of Justice",
        "Ancient Gear",
      ]
    };
  },
};
</script>

<style lang="scss" scoped>
    
</style>