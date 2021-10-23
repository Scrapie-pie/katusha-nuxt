<template>
  <BlockAbility class="block-ability_monitoring block-ability_reverse" v-bind="options">
    <IconLabel icon="pie-chart" type="aligned">Контроль расходных материалов на уровне серийных номеров</IconLabel>
    <IconLabel icon="trending-down" type="aligned">Снижение расходов на печать (минимум на 30%)</IconLabel>
    <IconLabel icon="shield" type="aligned">Система защиты информации и контроля печатаемых материалов</IconLabel>
    <IconLabel icon="tablet" type="aligned">Совместимость со всеми вендорами устройств</IconLabel>
  </BlockAbility>
</template>

<script>
export default {
  name: 'BlockAbilityBiometry',
  data: () => ({
    options: {
      subtitle: "Авторизация на принтерах и МФУ с помощью машинного зрения",
      image: require("@/src/images/skill04.png"),
      postscriptum: "Решение включено в единый реестр российского ПО приказом Минкомсвязи России №475 от 18.09.2018 года",
    }
  }),
}
</script>

<style lang="scss">
.block-ability {
  // &_monitoring & {
  //   &__container {
  //     grid-template-columns: minmax(300px, 910px) minmax(300px, auto);
  //     .content-side {
  //       order: -1;
  //     }
  //   }
  // }
}
</style>
