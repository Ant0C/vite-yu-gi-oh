<script>
export default {
}
</script>

<template>
  <header>
    <div class="row">
      <div class="col-2">
        <img src="/img/Yu-Gi-Oh!.svg" alt="">
      </div>
      <div class="col-8">
        <h1>Yu-Gi-Oh Api</h1>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use '../style/general.scss' as *;

header {
  padding: 15px;
}

.row {
  display: flex;
  align-items: center;
}

.col-2 {
  flex-basis: 10%;
  text-align: center;

  img {
    width: 50px;
    text-align: end;
  }
}

.col-8 {
  flex-basis: 80%;
}
</style>
