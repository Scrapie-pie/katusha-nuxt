<template>
  <div class="block-intro">
    <div class="block-intro__container">
      <!-- <h1>Экосистема корпоративной печати</h1> -->
      <div class="block-intro__description">
        «Катюша» предлагает решения для импортозамещения в сфере корпоративной печати. <br/>
        Подробнее со всеми продуктами и решениями можно ознакомиться на нашем сайте <BaseLink href="katusha-it.ru" type="underline">katusha-it.ru</BaseLink>
      </div>
      <BaseButton icon="airpay">Посетить демо зал Катюша в Мовква-сити</BaseButton>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockIntro',
}
</script>

<style lang="scss">
.block-intro {
  &__description {
    @include h(3, get-var(color, grey_dark));
    //margin-bottom: get-var(space, lg);
    margin-bottom: 75px;
  }
}
</style>
