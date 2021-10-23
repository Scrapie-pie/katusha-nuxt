<template>
  <div class="block-invite-form">
    <h3>Приглашение в демо-зал «Катюша»</h3>
    <form class="block-invite-form__form">
      <div class="block-invite-form__fields">
        <BaseField placeholder="Электронная почта" type="email" required/>
        <BaseField placeholder="Имя Фамилия" required/>
        <BaseField placeholder="Название компании" required/>
      </div>

      <div class="block-invite-form__options">
        <BaseField type="toggle" label="Посещение:"/>
        <BaseField type="date" label="Дата:" required/>
        <BaseField type="time" label="Время:" disabled/>

      </div>



      <div class="block-invite-form__order">
        <BaseField type="checkbox" required>
          Соласен с условиями <BaseLink>политики обработки персональных данных</BaseLink>
        </BaseField>
        <BaseButton>Оставить заявку</BaseButton>
      </div>


    </form>
  </div>
</template>

<script>

export default {
  name: 'BlockInviteForm',

}



</script>

<style lang="scss">






.block-invite-form {

  &__options {
    @include flex-container(row, 15px);
    flex-wrap: wrap;
    justify-content: space-between;
  }

  &__form {
    @include flex-container(column, 40px);
  }
  &__fields {
    @include flex-container(column, 30px);
  }

  &__order {
    padding-top: 25px;
    border-top: 1px solid get-variable(color, grey);
    display: grid;
    grid-template-columns: minmax(150px, 300px) auto;
    justify-content: space-between;
    grid-gap: 20px;
  }
}
</style>
