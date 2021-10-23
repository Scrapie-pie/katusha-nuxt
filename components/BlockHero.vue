<template>
  <div class="block-hero">
    <div class="block-hero__container">
      <BlockBanner class="block-hero__banner">
        <BlockDecentrilized>
          <template v-slot:left>
            <div class="block-hero__item">
              <div class="block-hero__article">
                <div>Сервер печати «КАТЮША» на процессоре Baikal M1-1000</div>
              </div>
              <img :src="image01"/>
            </div>
            <div class="block-hero__item">
              <div class="block-hero__article">
                <div>Линейка МФУ и принтеров «КАТЮША» с оригинальными расходными материалами</div>
              </div>
              <img :src="image02"/>
            </div>
            <div class="block-hero__item">
              <div class="block-hero__article">
                <div>Терминал управления доступом “Мониторинг и Защита”</div>
              </div>
              <img :src="image03"/>
            </div>
            <div class="block-hero__item">
              <div class="block-hero__article">
                <div>Авторизация на устройствах с помощью терминала распознавания лица - LUNA</div>
              </div>
              <img :src="image04"/>
            </div>
          </template>

          <template v-slot:top>
            <div class="decentralized__content">
              <div class="block-hero__article">
                Аутсорсинг печати Более 25000 аппаратов на контрактах аутсорсинга
              </div>
            </div>
          </template>

          <RouterCircle></RouterCircle>

          <template v-slot:right>
            <div class="block-hero__item">
              <img :src="image05"/>
              <div class="block-hero__article">
                <div>Сервер печати «КАТЮША» на процессоре Baikal M1-1000</div>
              </div>
            </div>
            <div class="block-hero__item">
              <img :src="image06"/>
              <div class="block-hero__article">
                <div>Линейка МФУ и принтеров «КАТЮША» с оригинальными расходными материалами</div>
              </div>
            </div>
            <div class="block-hero__item">
              <img :src="image07"/>
              <div class="block-hero__article">
                <div>Терминал управления доступом “Мониторинг и Защита”</div>
              </div>
            </div>
          </template>


        </BlockDecentrilized>

      </BlockBanner>
    </div>
  </div>
</template>

<script>

import CircleQuarter from '~/src/images/banner-circle/test.svg';


export default {
  name: 'BlockHero',
  data: () => ({
    image01: require('@/src/images/banner01.png'),
    image02: require('@/src/images/banner02.png'),
    image03: require('@/src/images/banner03.png'),
    image04: require('@/src/images/banner04.png'),
    image05: require('@/src/images/banner05.jpg'),
    image06: require('@/src/images/banner06.jpg'),
    image07: require('@/src/images/banner07.jpg'),
  }),
  components: {
    CircleQuarter,
  },
}
</script>

<style lang="scss">
$z1: 20px;



.block-hero {
  $r: &;

  &__item {
    @include flex-container(row);
  }

  &__banner {
    background-color: white;
  }

  &__article {
    position: relative;
    padding-left: 8px;
    margin-left: 10px;
    font-size: 14px;

    &:before {
      content: '';
      position: absolute;
      width: 10px;
      height: 10px;
      border-radius: 50%;
      top: .25em;
      border: 2px solid #242C5D;
      right: 100%;
    }
  }

  .decentralized {
    $d: '.decentralized';
    --decentralized-side-padding: 100px;


    &__position_left {
      #{$r}__item {
        grid-gap: 5px;
      }

      left: 0%;
      transition: .5s;
      //transform: translateX(0);

      #{$d}__item {
        &:nth-child(1) {
          --decentralized-item-width: 200px;
        }
        &:nth-child(2) {
          --decentralized-item-width: 235px;
        }
        &:nth-child(3) {
          --decentralized-item-width: 280px;
        }
        &:nth-child(4) {
          --decentralized-item-width: 250px;
        }
      }

      @media (max-width: 1400px) {
        //left: 50%;
        //transform: translateX(-100%);
      }
    }

    &__position_right {
      right: 0%;
      transition: .5s;

      #{$r}__item {
        grid-gap: 20px;

        img {
          max-width: 140px;
          width: 100%;
        }
      }

      @media (max-width: 1400px) {
        //right: 50%;
        //transform: translateX(100%);
      }

      --decentralized-item-width: 325px;
    }
  }
}

</style>
