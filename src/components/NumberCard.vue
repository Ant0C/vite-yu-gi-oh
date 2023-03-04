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
      <div class="select">
        <h4>Select archetype</h4>
        <select id="">
          <option value="Alien">Alien</option>
          <option value="Elemental HERO">Elemental HERO</option>
          <option value="ABC">ABC</option>
        </select>
      </div>

      <div class="content-info">
        Sono visibili <span class="num"> {{ Store.cards.length }} </span> carte
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../style/general.scss' as *;

.select {
  color: white;
  background-color: rgb(87, 81, 81);
  padding: 10px;
}

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
