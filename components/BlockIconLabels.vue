<template>
  <div class="icon-labels">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'BlockIconLabels',
}
</script>

<style lang="scss">
.icon-labels {
  @include flex-container(column, 30px);
  height: 100%;
  justify-content: center;
}
</style>
