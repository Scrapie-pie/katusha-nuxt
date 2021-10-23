<template>
  <footer class="footer">
    <div class="blocks"> <!-- mb replace on container ? -->
      <BlockAchievments/>
      <BlockFooter/>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'TheFooter',
}
</script>

<style lang="scss">
.footer {
  .blocks {
    grid-gap: 40px;
  }
}
</style>
