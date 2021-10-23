<template>
  <div class="content-side">
    <div class="content-side__main">
      <slot></slot>
    </div>
    <div class="content-side__bottom">
      <BlockPostscriptum v-if="postscriptum">
        {{postscriptum}}
      </BlockPostscriptum>
      <div class="content-side__actions">
        <slot name="actions">
          <BaseButton icon="youtube">Смотреть видео на YouTube</BaseButton>
        </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockContentSide',
  props: {
    postscriptum: String,
  },
}
</script>

<style lang="scss">
.content-side {
  width: 100%;
  height: 100%;
  @include flex-container(column);
  justify-content: space-between;

  &__main {
    height: 100%;
    @include flex-container(column)
  }
  &__main {
    //height: 100%;
    //margin-bottom: auto;
  }

  &__bottom {
    //@include flex-container(column, 35px);
  }

  &__actions {
    margin-top: 35px;
  }
}
</style>
