<template>
  <div class="block-invite-contacts">
    <div class="block-invite-contacts__info">
      <div class="block-invite-contacts__address">
        123112, Россия, г. Москва, Пресненская набережная д. 8, стр. 1
      </div>
      <div class="block-invite-contacts__contacts">
        <BaseContact value="+7 (495) 120 11 25" type="lg"/>
        <BaseContact value="mail@katusha-it.ru" type="lg"/>
      </div>
      <div class="block-invite-contacts__socials">
        <IconLabel icon="soc_facebook" type="soc">katushaprint</IconLabel>
        <IconLabel icon="soc_youtube" type="soc">Катюша Ай Ти</IconLabel>
        <IconLabel icon="soc_instagram" type="soc">katushaprint</IconLabel>
      </div>
    </div>
    <div class="block-invite-contacts__postscriptum">
      До встречи на территории инноваций «Катюша»!
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockInviteContacts',
}
</script>

<style lang="scss">
.block-invite-contacts {
  @include flex-container(column, 85px);

  &__info {
    @include flex-container(column, 35px);
  }

  &__address {
    font-size: 24px;
    font-weight: 300;
    color: get-variable(color, grey_dark)
  }

  &__contacts {
    padding: 35px 0;
    border-top: 1px solid get-variable(color, grey);
    border-bottom: 1px solid get-variable(color, grey);
    @include flex-container(row, 20px);
    justify-content: space-around;
    align-items: center;
  }

  &__socials {
    @include flex-container(row, 20px);
    justify-content: space-between;
    align-items: center;
    .icon_soc {
      &_facebook {
        color: #3A559F;
      }
      &_youtube {
        color: #DC472E;
      }
      &_instagram {
        color: #C536A4;
      }
    }
  }



  &__postscriptum {
    padding: 10px 15px;
    background-color: white;
    font-size: 18px;
    color: get-variable(color, grey_dark);
    text-align: center;
    border-radius: 10px;
  }
}
</style>
