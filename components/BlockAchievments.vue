<template>
  <div class="block-achievments">
    <div class="block-achievments__container">
      <div class="block-achievments__item">
        <div class="block-achievments__badge">
          <img src="~/../src/images/badge01.png" alt="image"/>
        </div>
        <span>ООО КАТЮША Ай Ти член Ассоциации разработчиков программных продуктов «Отечественный софт»</span>
      </div>
      <div class="block-achievments__item">
        <div class="block-achievments__badge">
          <img src="~/../src/images/badge02.png" alt="image"/>
        </div>
        <span>Исследования осуществляются ООО КАТЮША Ай Ти при грантовой поддержке Фонда «Сколково»</span>
      </div>
      <div class="block-achievments__item">
        <div class="block-achievments__badge">
          <img src="~/../src/images/badge03.png" alt="image"/>
          <div class="block-achievments__caption">
            АССОЦИАЦИЯ РАЗРАБОТЧИКОВ ПРОГРАММНЫХ ПРОДУКТОВ
          </div>
        </div>

        <span>ООО КАТЮША Ай Ти член Российского союза промышленников и предпринимателей</span>
      </div>
      <div class="block-achievments__item">
        <div class="block-achievments__badge">
          <img src="~/../src/images/badge04.png" alt="image"/>
          <div class="block-achievments__caption">
            Государственная информационная система промышленности
          </div>
        </div>
        <span>Решения «КАТЮША» рекомендованы МИНПРОМТОРГ РФ</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockAchievments',
  data() {
    return {
      badges: {
        //img: '~/src/images/badge01.png'
      }
    }
  }
}
</script>

<style lang="scss">
.block-achievments {

  &__container {
    display: grid; // test flex
    grid-template-columns: repeat(auto-fit, minmax(auto, 320px));
    justify-content: space-between;
    align-items: center;
    grid-gap: 25px;
    width: 100%;
  }


  &__item {
    @include flex-container(column, 15px);
    align-items: flex-start;
    font-size: 14px;
    color: get-variable(color, grey_dark);
  }

  &__badge {
    @include flex-container(row, 12px);
    font-size: 12px;
    font-weight: 700;
    align-items: center;
  }
}
</style>
