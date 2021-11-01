<template>
  <div class="block-footer">
    <div class="block-footer__container">
      <span>© 2021 КАТЮША Ай Ти. Все права защищены</span>
      <div class="block-footer__actions">

        <BaseContact value="mail@katusha-it.ru" type="sm"/>
        <BaseContact value="+7 (495) 120 11 25" type="sm"/>

        <a href="./index.html" class="block-footer__action" download>
          <BaseIcon icon="file_text"/>
          <span>Скачать презентацию</span>
        </a>

      </div>
      <span>Политика конфиденциальности</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheFooter',
}
</script>

<style lang="scss">
.block-footer {
  &__container {
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid get-var(color, grey);
    padding: 25px 0;
    font-size: 14px;

    & > * {
      &:first-child {
        justify-self: flex-start;
      }
      &:last-child {
        justify-self: flex-end;
      }
    }
  }


  &__actions {
    @include flex-container(row, to-unit(50px, em));
    align-items: center;
    justify-content: space-between;

    .icon {
      color: get-var(color, light);
    }
  }

  &__action {
    @include flex-container(row, 5px);
    align-items: center;
    font-size: 14px;
    &:hover {
      color: get-var(color, blue);
    }
    .icon {
      width: 20px;
      height: 17px;
    }
  }

}
</style>
