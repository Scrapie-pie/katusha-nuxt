<template>
  <div class="block-server-abilities">
    <h3>Возможности принт-сервера «Катюша»</h3>
    <div class="block-server-abilities__container">
      <IconLabel icon="codesandbox" type="aligned">Кросс-платформенное решение на архитектурах х86, х64, ARM и Эльбрус</IconLabel>
      <IconLabel icon="file" type="aligned">Оптимизация всех печатных процессов в компаниях любого масштаба</IconLabel>
      <IconLabel icon="refresh" type="aligned">Полная совместимость с российским ОС</IconLabel>
      <IconLabel icon="print" type="aligned">Поддержка всех устройств печати</IconLabel>
    </div>
    <BlockPostscriptum>Сервер доступен у дистрибьюторов компании «Катюша»</BlockPostscriptum>
  </div>
</template>

<script>







export default {
  name: 'BlockServerAbilities',
}
</script>

<style lang="scss">
.block-server-abilities {
  &__container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(215px, 1fr));
    grid-gap: 20px;

    .icon-label {
      .icon {
        max-width: none;
        width: 44px;
        height: 44px;
      }
      &__label {
        font-weight: 500;
      }
    }
    .icon-label .icon {
      max-width: none;
      width: 44px;
      height: 44px;
    }
  }
}
</style>
