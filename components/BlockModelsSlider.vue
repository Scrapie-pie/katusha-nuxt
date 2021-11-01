<template>
  <div class="block-models-slider">
    <div class="container">
      <BlockBanner>
        <SliderModels :models="models"/>
      </BlockBanner>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockModelsSlider',
  props: {
    models: {
      type: Array,
      required: true,
    }
  },
  data: () => ({
    swiperOptions: {
      //spaceBetween: 30,
    }
  }),
}

</script>

<style lang="scss">
.slider-models {
  $self: &;

  &__slide {
    justify-content: space-between;
    margin: 0 auto;
    width: 100%;
    //max-width: 1040px;
    display: grid;
    grid-template-columns: 425px 505px;
    //grid-template-columns: minmax(200px, 425px) minmax(250px, 505px);
    grid-gap: 30px;

    .icon-label__value {
      font-size: 18px;
      font-weight: 700;
    }
  }



  &__info {
    @include flex-container(column, 25px);
  }

  &__side {

  }
  &__wrapper {
    @include flex-container(column, 45px);
  }
  &__title {
    @include flex-container(column, 10px);
  }
  &__name {
    @include h(4);
  }
  &__alias {
    @include h(2);
  }
  &__about {
    @include flex-container(column, 15px);
  }
  &__description {
    font-size: 18px;
  }
  &__caption {
    font-size: 14px;
    color: get-var(color, grey_dark)
  }



  @media (max-width: 1100px) {
    &__image {
      display: flex;
      justify-content: center;
      img {
        max-width: 228px;
      }
    }
    &__slide {
      grid-template-columns: 1fr !important;
    }
  }
}
</style>
