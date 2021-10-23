<template>
  <div class="block-invite">
    <div class="block-invite__container">
      <BlockInviteForm/> <!-- SUBBLOCK -->
      <BlockInviteContacts/> <!-- SUBBLOCK -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockInvite',
}
</script>

<style lang="scss">
.block-invite {
  &__container {
    display: grid;
    grid-template-columns: minmax(auto, 620px) minmax(auto, 740px);

    // display: flex;
    // flex-wrap: wrap;
    justify-content: space-between;
    gap: 30px;
  }
}
</style>
