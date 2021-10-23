<template>
  <div class="banner">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'BlockBanner',
}
</script>

<style lang="scss">

.banner {
  @include flex-centralize;
  //background-color: get-variable(color, grey);
  padding: 55px;
  border-radius: 20px;
}
</style>
