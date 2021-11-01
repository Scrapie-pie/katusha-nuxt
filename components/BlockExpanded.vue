<template>
  <div class="expanded">
    <div class="expanded__wrapper">
      <slot></slot>
    </div>
    <div class="expanded__container">
      <div class="expanded__bottom">
        <slot name="bottom"></slot>
      </div>
      <slot name="postscriptum"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockExpanded',
}
</script>

<style lang="scss">

.expanded {
  &__wrapper {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    //grid-template-rows: 425px;
    img {
      width: 100%;
      height: 100%;
    }
  }

  &__bottom {
    padding-top: 50px;
    padding-bottom: 35px; // or 30
    border-bottom: 1px solid get-var(color, grey);
    margin-bottom: 30px;
  }
}
</style>
