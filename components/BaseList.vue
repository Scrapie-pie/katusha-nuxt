<template>
  <div class="list">
    <span v-if="title" class="list__title">
      {{title}}
    </span>
    <ul>
      <slot></slot>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'BaseList',
  props: {
    title: String,
  },
}
</script>

<style lang="scss">
.list {
  @include flex-container(column, 20px);
  font-weight: 300;

  &__title {
    color: get-variable(color, blue);
    font-size: 18px;
  }

  ul, ol {
    @include flex-container(column, 10px);
    list-style: none;
    margin: 0;
    padding: 0;
  }

  li {
    $icon-size:  4px;
    $icon-offset: 13px;

    position: relative;
    padding-left: calc(#{$icon-size} + #{$icon-offset});
    margin-left: 10px;

    &:before {
      content: '';
      position: absolute;
      top: .5em;
      left: 0;
      min-width:  $icon-size;
      min-height: $icon-size;
      max-width:  $icon-size;
      max-height: $icon-size;
      background-color: currentColor;
      border-radius: 50%;
    }
  }
}
</style>
