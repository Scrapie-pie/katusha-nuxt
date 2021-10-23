<template>
  <div class="block-ability" v-once>
    <div class="block-ability__container">
    <!-- <div class="tempo container"> -->


      <div class="block-ability__side">
        <img :src="image" class="block-ability__image" alt="image"/>
        <slot name="temp">

        </slot>
      </div>

      <BlockContentSide :postscriptum="postscriptum">
        <h3 v-if="subtitle" class="block-ability__subtitle">
          {{subtitle}}
        </h3>
        <div class="block-ability__content">
          <slot></slot>
        </div>
      </BlockContentSide>
    </div>

    <!-- </div> -->


  </div>
</template>

<script>
export default {
  name: 'BlockAbility',
  props: {
    subtitle: String,
    image: {
      type: String,
      required: true,
    },
    postscriptum: String,
  },
}
</script>

<style lang="scss">
.block-ability {
  $block-ability: &;

  &_reverse {
    #{$block-ability}__container {
      direction: rtl;
    }
    .content-side {
      direction: initial;
    }
  }

  &__container {

    display: grid;
    grid-template-columns: minmax(300px, auto) minmax(300px, 910px);

    //@include smart-grid((4f, 10f));

    //align-items: center;
    justify-content: space-between;
    gap: 30px;


  }

  .tempo {

    //grid-template-columns: minmax(300px, auto) minmax(300px, 910px);

    //@include smart-grid((3f, 4f) (4f, 8f));

  }


  &__subtitle + &__content {
    padding-top: 60px;
    border-top: 1px solid get-variable(color, grey);
  }
  // &__content {
  //   //height: 100%;
  //   margin-bottom: auto;
  //   padding-bottom: 40px;
  // }

  &__content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    justify-content: space-between;
    gap: 30px 50px;
    color: get-variable(color, grey_dark);
  }

  // &__actions {
  //   margin-top: 40px;
  // }

  &__image {
    border-radius: 10px;
    width: 100%;
  }

  &__more {
    @include flex-container(column, 35px);
  }

  &__advantages {
    @include flex-container(column, 30px);
  }

  @media (max-width: 1024px) { // Переход
    &__container {
      grid-template-columns: 1fr;
    }
    &__side {
      margin: 0 auto;
      img {
        max-width: 400px;
      }
    }
  }
}
</style>
