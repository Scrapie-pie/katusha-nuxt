<template>
  <header class="header">
    <div class="container">
      <div class="header__wrapper">
        <BaseIcon icon="logo"/>
        <nav class="header__nav">
          <a href="#" class="header__ref" v-scroll-to="{
            el: '.section-ecosystem'
          }">
            <BaseIcon icon="world"/>
            Экосистема
          </a>
          <a href="#" class="header__ref" v-scroll-to="{
            el: '.section-models'
          }">
            <BaseIcon icon="harddrive"/>
            Линейка “Катюша”
          </a>
          <a href="#" class="header__ref" v-scroll-to="{
            el: '.section-software'
          }">
            <BaseIcon icon="monitor"/>
            Программное обеспечение
          </a>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'TheHeader',
  props: {
    //msg: String
  }
}
</script>

<style lang="scss">
.header {
  background-color: get-var(color, white);
  box-shadow: 0px 0px 10px 0px rgb(0 0 0 / 8%);
  z-index: 10;
  //margin-bottom: 60px;

  &__wrapper {
    @include flex-container(row, 30px);
    justify-content: space-between;
    align-items: center;
    padding: 20px 0;
  }

  &__nav {
    //@include flex-container(row, 40px);
    //@include flex-container(row, get-var(space, xs));
    @include flex-container(row, (5px, 50px)); // temp

  }

  &__ref {
    @include flex-container(row, 10px);
    align-items: center;
    color: get-var(color, grey_dark);
    font-size: 18px;
    .icon {
      color: get-var(color, black);
    }
  }
}
</style>
