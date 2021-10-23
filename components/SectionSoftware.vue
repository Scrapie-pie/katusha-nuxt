<template>
  <section class="section-software">
    <h2>Встраиваемое программное обеспечение для устройств ведущих мировых производителей</h2>
    <BlockExpanded>
      <BaseVideo :preview="Image01"/>
      <BaseVideo :preview="Image02"/>
      <BaseVideo :preview="Image03"/>

      <template v-slot:bottom>
        <IconLabel icon="like">
          ПО “Мониторинг и Защита” соответствует требованиям актуального российского законодательства в области импортозамещения, внесено в Единый реестр российских программ для ЭВМ и БД (Приказ Минкомсвязи России №475 от 18.09.2018 г.)
        </IconLabel>
      </template>
    </BlockExpanded>

  </section>
</template>

<script>
export default {
  name: 'SectionSoftware',
  data: () => ({
    Image01: require('@/src/images/video01.jpg'),
    Image02: require('@/src/images/video02.jpg'),
    Image03: require('@/src/images/video03.jpg'),
    Image04: require('@/src/images/test.jpg'),
    Image05: require('@/src/images/test2.jpg'),
  }),
}

</script>

<style lang="scss">

</style>
