<template>
  <button class="button" v-ripple>
    <BaseIcon v-if="this.icon" :icon="this.icon"/>
    <slot></slot>
    </span>
  </button>
</template>

<script>
import Ripple from 'vue-ripple-directive';

Ripple.color = 'rgba(255, 255, 255, 0.15)';

export default {
  name: 'BaseButton',
  props: {
    icon: String,
  },
  directives: {
    ripple: Ripple,
  },
}
</script>

<style lang="scss">
.button {
  cursor: pointer;
  border: none;
  border-radius: 4px;

  box-sizing: border-box;

  padding: get-var(space, micro-sm) 35px;

  height: 50px;

  display: flex;
  //display: inline-flex;
  align-items: center;
  justify-content: space-between;

  background-color: get-var(color, blue);
  box-shadow: 0px 4px 16px rgba(0, 141, 210, 0.15); // cscs function hex opacity
  color: get-var(color, white);

  font-family: inherit;
  line-height: 1em;
  font-size: 20px;
  letter-spacing: 0.04em;

  //width: 100%;

  //width: min-content;
  white-space: nowrap;

  font-size: 20px;
  // &__label {
  //
  //   //font-weight: 500;
  // }
  max-width: fit-content;

  gap: 15px;

  &:active {
    //box-shadow: 0px 0px 5px rgb(0 0 0 / 30%) inset;
  }

  &_inline {
    display: inline-flex;
  }
}
</style>
