<script>
import { directive } from 'vue-awesome-swiper';
import 'swiper/css/swiper.css';

let swiper = null;

export default {
  name: 'AwesomeSwiper',
  render(h) {
    const items = this.$slots.default.map((vnode) => {
      return <div class="swiper-slide">{vnode}</div>
    })

    const arrows = this.arrows ? [
      <BaseIcon icon="arrow_left" nativeOnClick={this.prev}/>,
      <BaseIcon icon="arrow_right" nativeOnClick={this.next}/>
    ] : null;

    return (
      <div class="swiper">
        <div v-swiper={this.options} v-on:ready={this.init}>
          <div class="swiper-wrapper">
            {...items}
          </div>
        </div>
        {arrows}
      </div>
    )
  },
  props: {
    options: {
      type: Object,
      default: function() {
        return {
          slidesPerView: 1,
        }
      }
    },
    arrows: {
      type: Boolean,
      default: true,
    },
  },
  directives: {
    swiper: directive,
  },
  methods: {
    init(s) {
      swiper = s;
    },
    next() {
      swiper.slideNext()
    },
    prev() {
      swiper.slidePrev()
    }
  },
}
</script>

<style lang="scss">
.swiper {
  width: 100%;
  height: 100%;
  //position: relative;

  .icon_arrow {
    &_left, &_right {
      cursor: pointer;
      color: get-variable(color, white);
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: 14px;
      height: 24px;
      z-index: 2;
      font-size: 21px;
    }
    &_left {
      left: 30px;
    }
    &_right {
      right: 30px;
    }
  }
}
</style>
