<template>
  <figure class="router-circle" :style="style">


    <div class="router-circle__top">
      <div class="router-circle__chunk">
        <div class="router-circle__icon">
          <BaseIcon icon="handshake"/>
        </div>
        <CircleQuarter class="router-circle__figure"/>
        <div class="router-circle__content">
          <div class="router-circle__text">
            <div class="router-circle__title">
              Аутсорсинг печати
            </div>
            <div class="router-circle__description">
              Готовые решения
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="router-circle__left">
      <div class="router-circle__chunk">
        <div class="router-circle__icon">
          <BaseIcon icon="servers"/>
        </div>
        <CircleQuarter class="router-circle__figure"/>
        <div class="router-circle__content">
          <div class="router-circle__text">
            <div class="router-circle__title">
              АППАРАТНОЕ ОБЕСПЕЧЕНИЕ
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="router-circle__center">
      <BaseIcon icon="logo"/>
    </div>
    <div class="router-circle__right">
      <div class="router-circle__chunk">
        <div class="router-circle__icon">
          <BaseIcon icon="matrix"/>
        </div>
        <CircleQuarter class="router-circle__figure"/>
        <div class="router-circle__content">
          <div class="router-circle__text">
            <div class="router-circle__title">
              ПРОГРАММНОЕ ОБЕСПЕЧЕНИЕ
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="router-circle__bottom">
      <div class="router-circle__chunk">
        <div class="router-circle__icon">
          <BaseIcon icon="tools"/>
        </div>
        <CircleQuarter class="router-circle__figure"/>
        <div class="router-circle__content">
          <div class="router-circle__text">
            <div class="router-circle__title">
              Партнерский бизнес
            </div>
            <div class="router-circle__description">
              <div>Продажи</div>
              <div>Сервис</div>
              <div>Гарантия</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </figure>
</template>

<script>
import CircleQuarter from '~/src/images/banner-circle/test.svg';
//import CircleQuarter from '~/src/images/banner-circle/test2.svg';

let q;

export default {
  name: 'RouterCircle',
  components: {
    CircleQuarter,
  },
  data() {
    return {

      style: {
        transform: "scale(1)"
      },
    }
  },
  created() {
    window.addEventListener("resize", this.calcScale);
  },
  destroyed() {
    window.removeEventListener("resize", this.calcScale);
  },
  computed: {

  },
  methods: {
    calcScale(e) { // ебаный сколл учитывать
      let screenWidth = e.target.innerWidth;
      let scale = screenWidth / 1530;
      if (screenWidth > 1380 && scale < 1) {
        let k = 14;
        scale = Math.pow(k, scale) / k;
        this.style.transform = `scale(${scale})`;
      } else {
        this.style.transform = `scale(1)`;
      }

      //return { transform: `scale(${g})` }
      //$(window).width() / 1920) ;
      //"transform": "scale("+percentageOn1 +")
    }
  }
}
</script>

<style lang="scss">
.router-circle {
  $circle: &;
  //$size: to-unit(350px, em);
  $size: 350px;

  //@include to-responsive(font-size, 8px, $min-vw: 1200px, $max-vw: 1530px);

  width: 100%;
  min-width: $size;
  height: $size;
  position: relative;

  &__icon {
    $size: 60px;

    position: absolute;
    padding: 12px;
    border: 2px solid white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    min-width: $size;
    min-height: $size;
    width: $size;
    height: $size;
    right: 20%;
    top: 0;
    transform: translateY(-30%);
  }

  &__title {
    font-weight: 400;
  }

  &__description {
    font-size: 14px;
    margin: 0 auto;
  }

  &__text {
    color: white;
  }

  &__title {
    font-size: 12px;
    text-transform: uppercase;
    font-weight: 500;
  }

  &__content {
    display: flex;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    align-items: center;
    justify-content: center;
    position: absolute;
    z-index: 1;
    pointer-events: auto;
  }


  &__chunk {
    --top-gradient-start:    #217F9C;
    --top-gradient-stop:     #52BDBD;
    --left-gradient-start:   #F6A520;
    --left-gradient-stop:    #E63D29;
    --right-gradient-start:  #523E8E;
    --right-gradient-stop:   #8670B0;
    --bottom-gradient-start: #BD3879;
    --bottom-gradient-stop:  #ED6F98;
    left: 50%;
    transform: translateX(-50%);
    position: relative;
    //width: to-unit(249px, em);
    width: 249px;
  }

  &__figure {
    width: 100%;
  }

  &__center {
    $size: to-unit(106px, em);
    @include flex-centralize;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: $size;
    height: $size;
    border-radius: 50%;
    //border: 10px solid white;
    background: linear-gradient(0deg, #FEFEFE 4.86%, #C1C4CD 164.07%);
    box-sizing: content-box;
    z-index: 1;
    transition: .25s;

    .icon {
      transition: .25s;
      font-size: to-unit(94px, em);
    }

    &:hover {
      width: to-unit(122px, em);
      height: to-unit(122px, em);
      border-width: 0;

      .icon {
        font-size: to-unit(100px, em);
      }
    }
  }

  &__top, &__left, &__right, &__bottom {
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
  }

  &__top {
    #{$circle}__icon {
      background-color: #20ABCC;
      color: #007E89;
    }

    #{$circle}__content {
      max-width: 140px;
      width: 100%;
      padding: 8px;
    }

    // &:hover {
    //   --top-gradient-start: #52BDBD;
    //   --top-gradient-stop:  #217F9C;
    // }
  }

  &__left {
    $deg: 90.4deg;

    top: to-unit(-1px, em);
    transform: rotate(-#{$deg});

    #{$circle}__icon {
      background-color: #F18833;
      color: #DC5A21;
      transform: translateY(-30%) rotate($deg);
    }

    #{$circle}__content {
      padding: 10px 25px 10px 10px;
      transform: translate(-50%, -50%) rotate($deg);
    }
  }

  &__right {
    $deg: 89.6deg;

    top: to-unit(1px, em);
    transform: rotate($deg);

    #{$circle}__icon {
      background-color: #7E69AB;
      color: #4B4090;
      transform: translateY(-30%) rotate(-#{$deg});
    }

    #{$circle}__content {
      padding: 10px 10px 10px 25px;
      transform: translate(-50%, -50%) rotate(-#{$deg});
    }
  }

  &__bottom {
    $deg: 180deg;

    transform: rotate($deg);

    #{$circle}__icon {
      background-color: #E83C7B;
      color: #7F2444;
      transform: translateY(-30%) rotate(-#{$deg});
    }

    #{$circle}__content {
      max-width: 140px;
      width: 100%;
      padding: 8px;
      transform: translate(-50%, -50%) rotate(-#{$deg});
    }

    #{$circle}__description {
      max-width: 60px;
    }

    #{$circle}__text {
      margin-right: -25px;
      padding-top: 10px;
      width: 100%;
    }
  }



  @each $side, $i in (top, left, right, bottom) {
    #test_svg__gradient-#{$side} stop {
      &:first-child {
        stop-color: var(--#{$side}-gradient-start);
      }
      &:last-child {
        stop-color: var(--#{$side}-gradient-stop);
      }
    }
    .router-circle__#{$side} {
      .router-circle__figure {
        path {
          fill: url(#test_svg__gradient-#{$side});
        }
      }
    }

  }

  @media (max-width: 1380px) {

    //position: absolute;
    min-width: auto;
    max-width: none;
    width: 100%;
    height: auto;
    &__content {
      position: relative;
      top: auto;
      left: auto;
      background-color: red;
      transform: none !important;
      padding: 0 !important;
      max-width: none !important;
    }
    &__text {
      margin-right: 0 !important;
      padding-top: 0 !important;
      width: 100%;
    }
    &__description {
      margin: 0 !important;
      max-width: none !important;
    }
    &__top, &__left, &__right, &__bottom {
      position: relative;
      top: auto;
      left: auto;
      transform: none;
    }
    &__center {
      display: none;
    }

    &__chunk {
      left: auto;
      transform: none;
      width: 100%;
    }

    &__figure {
      display: none;
    }
  }
}

@media (max-width: 1380px) {
  .block-hero {
    .decentralized__position_middle {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      z-index: 1;
    }
  }
}



</style>
