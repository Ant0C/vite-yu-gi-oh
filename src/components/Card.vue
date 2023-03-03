<script>
export default {
  props: {
    card: {
      type: Object,
    }
  }
}
</script>

<template>
  <div>
    <!-- <img :src="card.card_images[0].image_url" alt=""> -->
  </div>
  <h3>
    {{ card.name }}
  </h3>
  <p>
    {{ card.archetype }}
  </p>
</template>

<style lang="scss" scoped>
@use '../style/general.scss' as *;
</style>
