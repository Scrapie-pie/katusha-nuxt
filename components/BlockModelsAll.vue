<template>
  <div class="block-models-all">
    <h3>Все модели</h3>
    <div class="block-models-all__container">
      <ElementModel
        v-for="(model, i) of models"
       :key="i"
       :name="model.name"
       :alias="model.alias"
       :format="model.labels.format.value"
       :caption="model.labels.print.value"
       :image="model.image"
       />
       <!-- <ElementModel
         v-for="(model, i) of models"
        :key="i"
        :name="model.name"
        :alias="model.alias"
        :format="model.labels.format.value"
        :caption="model.labels.print.value"
        :image="model.image"
        /> -->
    </div>

    <div class="test-grid">
      <div class="test-grid__container">
        <div>qweqweqe</div>
        <div>qweqweqe</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockModelsAll',
  props: {
    models: {
      type: Array,
      required: true,
    }
  }
}

</script>

<style lang="scss">
.block-models-all {
  &__container {
    display: grid;
    gap: 30px 35px;
    background-color: blue;

    @include smart-grid(8); //work
    //@include smart-grid((110px, 9)); //work
    //@include smart-grid((9, 100px)); //work
    //@include smart-grid(200px); //work
    //@include smart-grid((130px, 200px)); // work
    //@include smart-grid([0.5, 5, 200px]); // work

    //@include smart-grid((auto, 7)); //work
    //@include smart-grid((auto, 200px)); // work
    //@include smart-grid((auto, 5, 200px)); // work

    //@include smart-grid((0.5, 9)); //work
    //@include smart-grid((0.5, 180px)); //work
    //@include smart-grid((0.5, 5, 200px)); // work

    //@include smart-grid((9, 3)); // Значит 9 колонок, и тянем по 3 каждую -> ДОБАВИТЬ

    //@include smart-grid((auto, 12, 12/8), $mode: 'span'); // work
    //@include smart-grid((130px, 12, 12/6), $mode: 'percent'); // work
  }

  .test-grid {
    &__container {
      margin-top: 100px !important;

      display: grid;
      gap: 30px 35px;
      background-color: yellow;

      //@include smart-grid([(100px, 200px), (100px, 200px)]);
    }
  }
}


</style>
