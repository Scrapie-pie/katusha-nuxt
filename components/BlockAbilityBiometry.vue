<template>
  <BlockAbility class="block-ability_biometry" v-bind="options">
    <IconLabel icon="check_circle">Документы печатаются на том принтере, к которому вы подойдёте</IconLabel>
    <IconLabel icon="check_circle">Нет карт и паролей, которые можно потерять, забыть, передать</IconLabel>
    <IconLabel icon="check_circle">Печатайте без очередей и задержек на освободившихся устройствах</IconLabel>
    <IconLabel icon="check_circle">Документы не попадают в чужеие руки, все задания печатаются при вас</IconLabel>

    <template v-slot:actions>
      <BaseButton icon="youtube">Смотреть видео на YouTube</BaseButton>
    </template>
  </BlockAbility>
</template>

<script>
export default {
  name: 'BlockAbilityBiometry',
  data: () => ({
    options: {
      title: "Биометрическое распознавание лица",
      subtitle: "Авторизация на принтерах и МФУ с помощью машинного зрения",
      image: require("@/src/images/skill01.png")
    }
  })
}
</script>

<style lang="scss">

</style>
