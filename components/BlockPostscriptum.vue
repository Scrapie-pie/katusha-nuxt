<template>
  <div class="postcriptum">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'BlockPostscriptum',
}
</script>

<style lang="scss">
.postcriptum {
  margin-top: 30px;
  padding-top: 10px;
  border-top: 1px solid get-variable(color, grey);
  color: get-variable(color, grey_dark);
  font-weight: 300;
  font-size: 14px;

  @include container;

  &::before {
    content: '* ';
  }
}
</style>
