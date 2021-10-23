<template>
  <BaseSection className="section-mobile-auth">
    <div class="section-mobile-auth__wrapper">
      <BlockCapabilityMobile/>
    </div>

  </BaseSection>
</template>

<script>
export default {
  name: 'SectionMobAuth'
}

</script>

<style lang="scss">
.section-mobile-auth {
  &__wrapper {
    @include flex-container(column, 140px);
  }

  .capability {
    &:nth-child(odd) .capability__wrapper {
      grid-template-columns: minmax(300px, auto) minmax(300px, 910px);
    }
    &:nth-child(even) .capability__wrapper {
      grid-template-columns: minmax(300px, 910px) minmax(300px, auto);
      & > *:last-child {
        order: -1;
      }

    }
  }
}
</style>
