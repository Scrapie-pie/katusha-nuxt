<template>
  <div class="block-server-banner">
    <div class="container">


      <BlockBanner>
        <BlockDecentrilized>
          <template v-slot:left>
            <div class="block-server-banner__item">
              <img :src="Image1"/>
            </div>
            <div class="block-server-banner__item">
              <img :src="Image2"/>
            </div>
            <div class="block-server-banner__item">
              <img :src="Image3"/>
            </div>
            <div class="block-server-banner__item">
              <img :src="Image4"/>
            </div>
            <div class="block-server-banner__item">
              <img :src="Image5"/>
            </div>
          </template>

          <div class="block-server-banner__main">
            <img :src="ImagePrint"/>
          </div>
        </BlockDecentrilized>

        <BlockContentSide>
          <BlockIconLabels>
            <IconLabel icon="chip">Центральный процессор “Байкал ВЕ-М 1000”</IconLabel>
            <IconLabel icon="box">Материнская плата “Эдельвейс”</IconLabel>
            <IconLabel icon="server">ОС Astra linux “Новороссийск”</IconLabel>
            <IconLabel icon="shield">СПО “Мониторинг и Защита”</IconLabel>
            <IconLabel icon="data">СУБД “PostgreSQL”</IconLabel>
          </BlockIconLabels>
        </BlockContentSide>

      </BlockBanner>
    </div>
  </div>
</template>

<script>







export default {
  name: 'BlockServerBanner',
  data: () => ({
    ImagePrint: require('@/src/images/print-server.png'),
    Image1: require('@/src/images/qwe/01.png'),
    Image2: require('@/src/images/qwe/02.png'),
    Image3: require('@/src/images/qwe/03.png'),
    Image4: require('@/src/images/qwe/04.png'),
    Image5: require('@/src/images/qwe/05.png'),
  }),
  components: {
  }
}
</script>

<style lang="scss">
.block-server-banner {
  $width: 245px;

  $self: &;


  @include flex-container(column, 100px);

  .banner {
    background-color: get-var(color, grey);
    display: grid;
    //grid-template-columns: minmax(450px, 850px) minmax(200px, 460px);
    grid-template-columns: 1fr minmax(200px, 460px);
    grid-gap: to-unit(80px, em);
    justify-content: space-between;
  }

  &__main {
    width: 100%;
    img {
      width: 344px;
    }
    @media (max-width: 1530px) {
      img {
        width: to-unit(344px, vw);
      }

    }
  }

  &__item {
    @include flex-centralize;
    background-color: white;
    padding: 12px 20px;
    border-radius: 10px;
    width: 100%;
    height: 90px;
    //object-fit: contain;
    //max-width: 245px;
  }

  .decentralized__position_left {
    @media (max-width: 1530px) {
      --decentralized-side-padding: #{to-unit(130px, vw)};
      --decentralized-item-width: #{to-unit(245px, vw)};
      --decentralized-item-space: #{to-unit(30px, vw)};
    }


    // --decentralized-side-padding: #{to-unit(130px, rem)};
    // --decentralized-item-width: #{to-unit(245px, rem)};
    // --decentralized-item-space: #{to-unit(30px, rem)};
  }

  @media (max-width: 1400px) {
    #{$self}__item img {
      width: 100%;
      object-fit: scale-down;
    }
  }
}
</style>
