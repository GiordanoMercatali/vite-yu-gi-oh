<script>
export default {
  props: {
    card: Object,
  },
};
</script>

<template>
  <div class="mb-4 text-center">
    <!-- <img :src="card.image" alt="" /> -->
    <h3>{{ card.name }}</h3>
    <p class="text-primary">{{ card.type }}</p>
    <p class="text-secondary">{{ card.race }}</p>
    <p class="text-success">{{ card.attribute }}</p>
  </div>
</template>

<style lang="scss" scoped></style>