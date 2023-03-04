<script>
export default {
  props: {
    card: {
      type: Object,
      required: true,
    }
  }
}
</script>

<template>
  <li class="row card">
    <img :src="card.card_images[0].image_url" alt="">
    <span class="card-name">
      {{ card.name }}
    </span>
    <span class="card-archetype">
      {{ card.archetype }}
    </span>
  </li>
</template>

<style lang="scss" scoped>
@use '../style/general.scss' as *;

.card {
  align-items: center;
  font-size: 13px;
  background-color: bisque;

  .card-name {
    margin-top: 15px;
  }

  .card-archetype {
    margin-top: 15px;
    text-align: center;
    font-size: 15px;
    font-weight: 800;
  }
}
</style>
