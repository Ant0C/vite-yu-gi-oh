<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import NumberCard from './components/NumberCard.vue'


export default {
  components: {
    Header,
    NumberCard,
    Main,
  }
}
</script>

<template>
  <Header></Header>
  <NumberCard></NumberCard>
  <Main></Main>
</template>

<style lang="scss">
@use './style/general.scss';
</style>
