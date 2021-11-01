<template>
  <div class="element-model" v-once>
    <div class="element-model__preview">
      <img :src="image"/>
      <div class="element-model__format">{{format}}</div>
    </div>
    <div class="element-model__description">
      <div class="element-model__name">{{name}} {{alias}}</div>
      <div class="element-model__caption">{{caption}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ElementModel',
  props: {
    name: {
      type: String,
      required: true,
    },
    alias: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
    format: {
      type: String,
      required: true,
    },
    caption: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="scss">
.element-model {
  @include flex-container(column, 15px);

  height: 395px;

  &__preview {
    @include flex-centralize;
    background-color: get-var(color, grey);
    height: 320px;
    border-radius: 10px;
    padding: 30px;
    position: relative;

    img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }

  &__format {
    @include flex-centralize;
    position: absolute;
    bottom: 8px;
    right: 8px;
    font-weight: 500;
    font-size: 18px;
    padding: 5px;
    // width: 32px;
    // height: 32px;
    border-radius: 4px;
    background-color: get-var(color, white);
    color: get-var(color, blue);
  }

  &__description {
    @include flex-container(column, 5px);
    font-weight: 300;
  }

  &__name {
    font-size: 20px;
    color: black;
  }

  &__caption {
    font-size: 16px;
    color: get-var(color, grey_dark);
  }


}
</style>
