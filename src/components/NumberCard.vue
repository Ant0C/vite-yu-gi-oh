<script>
import Store from '../Store.js';

export default {
  data() {
    return {
      Store
    }
  },
}
</script>

<template>
  <div class="container">
    <div class="row">
      <div class="content-info">
        Sono visibili <span class="num"> {{ Store.cards.length }} </span> carte
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../style/general.scss' as *;


.content-info {
  background-color: rgb(36, 35, 35);
  color: white;
  padding: 10px;

  .num {
    color: yellow;
    font-size: 20px;
  }
}
</style>
