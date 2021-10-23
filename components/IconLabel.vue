<template>
  <div :class="selector">
    <div class="icon-label__icon">
      <BaseIcon :icon="icon"/>
    </div>
    <div class="icon-label__label">
      <slot></slot>
      <span v-if="name" class="icon-label__name">
        {{name}}
      </span>
      <span v-if="value" class="icon-label__value">
        {{value}}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IconLabel',
  props: {
    icon: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      default: 'box',
      validator: (value) => ['box', 'aligned', 'soc'].includes(value)
    },
    name: String,
    value: String,
  },
  computed: {
    selector() {
      return this.type ? `icon-label icon-label_${this.type}` : 'icon-label';
    }
  }
}
</script>

<style lang="scss">
.icon-label {
  $self: &;

  align-items: center; // move flex here, change only grid-gap

  &__icon {
    $size: 48px;
    @include flex-centralize;
    min-width:  $size;
    min-height: $size;
    max-width:  $size;
    max-height: $size;
    .icon {
      //color: get-variable(color, blue);
    }
  }

  &__label {
    @include flex-container(column, 5px);
    font-size: to-unit(18px, em);
    font-weight: 300;
  }

  &__name {
    color: get-variable(color, grey_dark);
  }

  &__value {
    @include h(3);
  }

  &_box {
    @include flex-container(row, to-unit(25px, em));
    #{$self}__icon {
      padding: 5px;
      background-color: get-variable(color, white);
      border-radius: 10px;
      color: get-variable(color, blue);
    }

    #{$self}__label {
      color: get-variable(color, black);
    }
  }

  &_aligned {
    @include flex-container(row, to-unit(25px, em));
    #{$self}__icon {
      color: get-variable(color, blue);
      .icon {
        max-width: none;
        height: 38px;
        width: 44px;
        // take the maximum width and maximum height. PROFIT!
      }
    }

    #{$self}__label {
      color: get-variable(color, grey_dark);
    }
  }

  &_soc {
    //align-items: center;
    @include flex-container(row, to-unit(15px, em));
    .icon {
      border-radius: 4px;
    }

    #{$self}__label {
      font-size: 18px;
      color: get-variable(color, grey_dark);
    }
  }

  // &_form & {
  //   &__icon {
  //     .icon {
  //       max-width: none;
  //       height: 38px;
  //       width: 44px;
  //       // take the maximum width and maximum height. PROFIT!
  //     }
  //   }
  //
  //   &__label {
  //     color: get-variable(color, grey_dark);
  //   }
  // }
}
</style>
