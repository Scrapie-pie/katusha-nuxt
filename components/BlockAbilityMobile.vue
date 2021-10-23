<template>
  <BlockAbility class="block-ability_mobile" v-bind="options">

    <template v-slot:temp>
      <div class="block-ability__download-app">
        <a href='#'>
          <img :src="googlePlayImg" />
        </a>
        <a href='#'>
          <img :src="appStoreImg" />
        </a>
      </div>

    </template>

    <div class="block-ability__more">
      <IconLabel icon="plus_circle" name="Больше" value="Возможностей"/>
      <IconLabel icon="plus_circle" name="Больше" value="Безопасности"/>
      <IconLabel icon="plus_circle" name="Больше" value="Экономии"/>
    </div>

    <div class="block-ability__advantages">
      <BaseList title="Технологические преимущества:">
        <li>Совместимость со всеми моделями принтеров и МФУ</li>
        <li>Биометрические данные неотъемлемы от сотрудника</li>
        <li>Легкость внедрения и эксплуатации</li>
      </BaseList>
      <BaseList title="Просто использовать:">
        <li>Подойдите к любому принтеру в офисе</li>
        <li>Посмотрите в камеру, нажмите кнопку</li>
        <li>Заберите ваши документы</li>
      </BaseList>
    </div>

  </BlockAbility>
</template>

<script>
export default {
  name: 'BlockAbilityMobile',
  data: () => ({
    options: {
      image: require("@/src/images/skill03.png"),
      postscriptum: "Решение включено в единый реестр российского ПО приказом Минкомсвязи России №475 от 18.09.2018 года",
    },
    googlePlayImg: require('@/src/images/google-play.png'),
    appStoreImg: require('@/src/images/app-store.png'),
  }),
}
</script>

<style lang="scss">
.block-ability {
  &_mobile & {
    grid-template-columns: auto 400px;

    &__download-app {
      padding-top: 5px;
      @include flex-container(row, 25px);
      align-items: center;
      justify-content: center;
    }
  }
}
</style>
