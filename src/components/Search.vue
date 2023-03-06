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
  <div class="select">
    <input type="text" placeholder="search" v-model="Store.search" @keyup.enter="$emit('filter')">
  </div>
</template>

<style lang="scss" scoped>
@use '../style/general.scss' as *;


.select {
  color: white;
  background-color: rgb(87, 81, 81);
  padding: 10px;
}
</style>
