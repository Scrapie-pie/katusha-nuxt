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
    //grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    //@include smart-grid([(100px 1fr)], 12);
    //@include smart-grid([(160px 1fr)], 8);
    //@include smart-grid($len: 8);


    //@include smart-grid(8);
    //@include smart-grid((180px, 8));
    @include smart-grid(200px);
    //@include smart-grid((180px, 200px));
    //@include smart-grid((auto, 200px));
    //@include smart-grid((180px, auto));
    //@include smart-grid((8, 200px));
    //@include smart-grid((180px, 8, 200px));

  }
}
</style>
