<template>
  <section class="section-server">
    <h1>Принт-сервер «Катюша»</h1>
    <div class="blocks">
      <BlockServerBanner/>
      <BlockServerAbilities/>
    </div>
  </section>
</template>

<script>







export default {
  name: 'SectionServer',
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
.print-server {

}
</style>
