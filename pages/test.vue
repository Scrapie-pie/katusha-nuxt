<template>
  <!-- <BaseSection></BaseSection> -->
  <ul>
    <li v-for="name in names">
      <BaseIcon :icon="name"/>
      {{name}}
    </li>
  </ul>
</template>

<script>
//import BaseSection from '~/components/BaseSection.vue';
let names = require('~/src/icons/actualtest/generated/names.json');
console.log(names)

export default {

  data() {
    return {
      names
    }
  }
  // components: {
  //   BaseSection,
  // }

}
</script>

<style lang="scss">
//@include setup-font('../src/fonts', 'PFDinDisplayPro', ('woff', 'ttf', 'eot'));

body {
  //font-family: 'PFDinDisplayPro';
}

</style>
