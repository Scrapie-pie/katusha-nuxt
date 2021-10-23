<template>
  <div class="block-distributors">
    <div class="block-distributors__container">
      <div class="block-distributors__caption">
        Техника и ПО в наличии у дистрибуторов компании «Катюша»
      </div>
      <AwesomeSwiper :options="swiperOptions" :arrows="false">
        <img v-for="(distributor, i) of distributors" :key="i" :src="distributor"/>
      </AwesomeSwiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockDistributors',
  data: () => ({
    distributors: [
      require('@/src/images/distributors/distributor01.png'),
      require('@/src/images/distributors/distributor02.png'),
      require('@/src/images/distributors/distributor03.png'),
      require('@/src/images/distributors/distributor03.png'),
      require('@/src/images/distributors/distributor03.png'),
      require('@/src/images/distributors/distributor03.png'),
      require('@/src/images/distributors/distributor03.png'),
      require('@/src/images/distributors/distributor03.png'),
      require('@/src/images/distributors/distributor03.png'),
    ],
    swiperOptions: {
      slidesPerView: 3,
      slidesPerGroup: 3,
      freeMode: true,
      //centeredSlides: true,
      spaceBetween: 30,
    }
  }),
}

</script>

<style lang="scss">
.block-distributors {
  $self: &;

  &__container {
    display: grid;
    //grid-template-columns: 1fr minmax(min-content, 1000px);
    grid-template-columns: 260px minmax(0, 1000px);
    justify-content: space-between;
    // padding: 35px 0;
    border-top: 1px solid get-variable(color, grey);
    border-bottom: 1px solid get-variable(color, grey);

    grid-gap: 30px;

    @include to-responsive((
      padding-top: (25px, 35px),
      padding-bottom: (25px, 35px),
    ));

  }

  .swiper {
    filter: grayscale(1);
    opacity: .45;
    &-wrapper {
      justify-content: space-between;
    }
    &-slide {
      //max-width: 155px;
      width: 100%;
      user-select: none;
    }
  }

  .swiper-slide {

  }

  &__caption {
    max-width: 260px;
    color: get-variable(color, grey_dark);
    line-height: 1.5em
  }

  @media (max-width: 768px) {
    #{$self}__container {
      grid-template-columns: 1fr;
    }
  }

}
</style>
