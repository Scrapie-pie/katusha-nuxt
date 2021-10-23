<template>
  <div class="block-contacts">
    <div class="block-contacts__container">
      <div class="block-contacts__content">
        <h2>ООО «Катюша Ай Ти»</h2>
        <div class="block-contacts__info">
          <div class="block-contacts__contacts">
            <BaseContact value="+7 (495) 120 11 25" type="lg"/>
            <BaseContact value="mail@katusha-it.ru" type="lg"/>
          </div>
          <div class="block-contacts__dynamic">
            <div class="block-contacts__address">
              123112, Россия, г. Москва, Пресненская набережная д. 8, стр. 1
            </div>
            <div class="block-contacts__tabs">
              <div class="block-contacts__tab">
                ММДЦ «Москва-Сити»
              </div>
              <div class="block-contacts__tab">
                МФК «Город Столиц»
              </div>
            </div>
          </div>
        </div>
      </div>

      <YandexMaps :coords="this.coords" :placemarks="this.items" :zoom="this.zoom"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockContacts',
  props: {},
  data() {
    return {
      zoom: 15,
      items: [
        [55.747286, 37.539099],
      ],
      coords: [55.747286, 37.539099]
    };
  },
}
</script>

<style lang="scss">
.block-contacts {
  &__container {
    display: grid;
    grid-template-columns: 340px auto;
    height: 500px;
    gap: 30px;
  }
  &__content {
    @include flex-container(column, 55px, $collapse: true);
  }
  &__title {
    //margin-bottom: 55px;
  }
  &__info {
    width: 100%;
    max-width: 315px;
    @include flex-container(column, 60px);
  }
  &__contacts {
    //margin: 55px 0 60px;
    @include flex-container(column, 20px);
    padding-top: 25px;
    border-top: 1px solid get-variable(color, grey);
  }
  &__dynamic {
    @include flex-container(column, 25px);
    color: get-variable(color, grey_dark);
  }
  &__address {
    font-size: 20px;
    padding-bottom: 20px;
    border-bottom: 1px solid get-variable(color, grey);
    font-weight: 300;
  }
  &__tabs {
    font-size: 14px;
    font-weight: 300;
    //display: grid;
    //grid-template-columns: repeat(auto-fit, minmax(135px, 1fr));
    //gap: 15px;
    @include flex-container(row, 15px);
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;

    // & > * {
    //   &:first-child {
    //     justify-self: flex-start;
    //   }
    //   &:last-child {
    //     justify-self: flex-end;
    //   }
    // }
  }

}
</style>
