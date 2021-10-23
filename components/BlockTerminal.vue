<template>
  <div class="block-terminal">
    <BlockExpanded>
      <BaseVideo :preview="Image04"/>
      <img :src="Image05" />
      <img :src="Image02" />

      <template v-slot:bottom>
        <div class="block-terminal__content">
          <img :src="ImageBottom"/>
          <div class="block-terminal__side">
            <IconLabel icon="like">
              Первый российский терминал управления доступом “Мониторинг и Защита” работает со всеми моделями многофункциональных устройств и серверных принтеров
            </IconLabel>
            <IconLabel icon="like">
              Объединение всех функций мониторинга и печати в единую унифицированную систему обеспечивает четкую и удобную работу с минимумом инсталляций и не сложным управлением
            </IconLabel>
          </div>
        </div>
      </template>

      <template v-slot:postscriptum>
        <span>Протестировать внешний терминал «Катюша» в <BaseLink>демозале</BaseLink></span>
      </template>
    </BlockExpanded>

  </div>
</template>

<script>
export default {
  name: 'BlockTerminal',
  data: () => ({
    Image01: require('@/src/images/terminal01.jpg'),
    Image02: require('@/src/images/terminal02.jpg'),
    Image03: require('@/src/images/video04.jpg'),
    ImageBottom: require('@/src/images/terminal-bottom.jpg'),
    Image04: require('@/src/images/test.jpg'),
    Image05: require('@/src/images/test2.jpg'),
  }),
}

</script>

<style lang="scss">
.block-terminal {
  &__content {
    display: grid;
    grid-template-columns: auto 1040px;
    grid-gap: 30px;
  }

  &__side {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    grid-gap: 15px;

    .icon-label {
      align-items: flex-start;
      &__label {
        line-height: 2em;
        font-size: 16px;
      }
    }
  }
}
</style>
