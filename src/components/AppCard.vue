<script>
export default {
  props: {
    card: Object,
  },
};
</script>

<template>
  <div class="mb-4 text-center">
    <img :src="card.card_images[0].image_url_small" alt="" />
    <h3>{{ card.name }}</h3>
    <p class="text-primary">{{ card.type }}</p>
    <p class="text-secondary">{{ card.race }}</p>
    <p class="text-success">{{ card.attribute }}</p>
    <p class="text-danger">{{ card.archetype ? card.archetype: "None"}}</p> <!--Archetipo esiste ? Sì (fai questo) : No (fai altro)-->
  </div>
</template>

<style lang="scss" scoped></style>