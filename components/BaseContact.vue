<template>
  <a :href="href" :class="['contact', typeSelector]" v-once>
    <BaseIcon :icon="icon"/>
    {{value}}
  </a>
</template>

<script>
export default {
  name: 'BaseContact',
  props: {
    value: {
      type: String,
      required: true,
      validator: (value) => determineType(value)
    },
    type: {
      type: String,
      validator: (value) => ['sm','lg'].includes(value)
    }
  },
  computed: {
    hrefType() {
      return determineType(this.value);
    },
    href() {
      return this.hrefType === 'mail' ?
        `mailto:${this.value}` :
        `tel:${formatTel(this.value)}`;
    },
    icon() {
      return this.hrefType === 'mail' ? 'mail' : 'phone';
    },
    typeSelector() {
      console.log(this.type)
      return this.type ? `contact_${this.type}` : null;
    }
  },
}

function formatTel(value) {
  return value.replace(/[\(|\)|-|\s]/g, '');
}

function determineType(value) {
  let isEmail = /^[\w|\d|-]+@[\w|\d|-]+\.\w+$/.test(value);
  let isTel = !formatTel(value)
    .replace(/^\+/, '')
    .split('')
    .map(x => x == 0 ? 0 : (parseInt(x) || x))
    .filter(char => typeof(char) !== 'number')
    .length;

  return isEmail ? 'mail' : isTel ? 'tel' : null;
}
</script>

<style lang="scss">
.contact {
  @include flex-container(row, .45em);
  align-items: center;

  &_lg {
    font-size: 28px;
    color: get-var(color, blue);
    &:hover {
      .icon {
        color: currentColor;
      }
    }
    .icon {
      color: get-var(color, black);
    }
  }

  &_sm {
    &:hover {
      color: get-var(color, blue);
    }
    .icon {
      width: 20px;
      height: 17px;
    }
  }
}
</style>
