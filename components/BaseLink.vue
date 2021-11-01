<template>
  <a :class="['link', typeSelector]" :href="href">
    <slot></slot>
  </a>
</template>

<script>

export default {
  name: 'BaseLink',
  props: {
    href: {
      type: String,
      default: '#'
    },
    type: {
      type: String,
    }
  },
  computed: {
    typeSelector() {
      return this.type ? `link_${this.type}` : null;
    }
  }
}
</script>

<style lang="scss">
.link {
  color: get-var(color, blue);

  &_underline {
    text-decoration: underline;
  }
}
</style>
