<template>
  <div class="block-videomaterials">
    <div class="block-videomaterials__container">
      <h3>Видеоматериалы</h3>
      <div class="block-videomaterials__wrapper">
        <BaseVideo caption="qweqeq"/>
        <BaseVideo :preview="Image04" caption="qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq qweqeq"/>
        <BaseVideo :preview="Image05" caption="qweqeq"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockVideoMaterials',
  data: () => ({
    Image04: require('@/src/images/test.jpg'),
    Image05: require('@/src/images/test2.jpg'),
  }),
}
</script>

<style lang="scss">
.block-videomaterials {

  .video__cover {
    border-radius: 10px;
    overflow: hidden;
  } // вынести в компонент

  .video__caption {
    @include truncate(1);
  }

  &__wrapper {
    display: grid;
    grid-template-columns: repeat(3, 1fr);

    //@include smart-grid([(300px, 1fr)], 3);
    grid-gap: 30px;

    grid-template-rows: 365px;

    @media (max-width: 1006px) {
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      & > * {
        &:last-child {
          grid-column: 1/-1;
          height: 125%;
        }
        &:nth-child(2n + 2) {
          grid-column: auto;
        }
      }
    }
  }

}
</style>
