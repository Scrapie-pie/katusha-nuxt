<template>
  <BaseSection className="capabilities">
    <div class="capabilities__wrapper">
      <BlockCapabilityBiometry/>
      <BlockCapabilityMonitoring/>
    </div>

  </BaseSection>
</template>

<script>
export default {
  name: 'SectionCapabilities'
}

</script>

<style lang="scss">
.capabilities {
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
