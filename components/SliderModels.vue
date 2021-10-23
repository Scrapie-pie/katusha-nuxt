<template>
  <!-- <BlockBanner>
    <SliderModels :models="models"/>
  </BlockBanner> -->

  <AwesomeSwiper :arrows="true">
    <div class="slider-models__slide" v-for="(model, i) of models" :key="i">
      <div class="slider-models__image">
        <img :src="model.image" />
      </div>
      <BlockContentSide class="slider-models__side">
        <div class="slider-models__wrapper">
          <div class="slider-models__info">
            <div class="slider-models__title">
              <span class="slider-models__name">{{model.name}}</span>
              <span class="slider-models__alias">{{model.alias}}</span>
            </div>
            <div class="slider-models__about">
              <div class="slider-models__description">
                {{model.description}}
              </div>
              <div class="slider-models__caption">
                {{model.caption}}
              </div>
            </div>
          </div>

          <BlockIconLabels>
            <IconLabel
              v-for="(label, i) in model.labels"
              :key="i"
              :icon="label.icon"
              :name="label.name"
              :value="label.value"
            />
          </BlockIconLabels>
        </div>


      </BlockContentSide>
    </div>
  </AwesomeSwiper>
</template>

<script>
export default {
  name: 'SliderModels',
  props: {
    models: {
      type: Array,
      required: true,
    }
  }
}

</script>

<style lang="scss">
.slider-models {

  &__slide {
    justify-content: space-between;
    margin: 0 auto;
    width: 100%;
    max-width: 1040px;
    display: grid;
    grid-template-columns: 425px 505px;
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
    color: get-variable(color, grey_dark)
  }


}
</style>
