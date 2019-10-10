<template>
  <div>
    <div class="l-container">
      <nuxt />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "~/assets/scss/mixins.scss";
.l-container {
  @include container;
}
</style>
