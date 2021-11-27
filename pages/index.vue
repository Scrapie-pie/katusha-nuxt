<template>
  <main>
    <SectionEcoSystem/>
    <SectionModels/>
    <SectionServer/>
    <SectionTerminal/>
    <SectionBiometry/>
    <SectionMonitoring/>
    <SectionSoftware/>
    <SectionMobile/>
    <SectionInvite/>
    <!-- <SectionContacts/> -->
  </main>
</template>

<style lang="scss">
main {
  @include flex-container(column);
  margin-bottom: get-var(space, xl);

  @include to-responsive((
    grid-gap: (60px, 140px),
    padding-top: (30px, 60px)
  ));
}

h1, h2, h3, h4, h5, h6 {
  $h: &;
  @include container;
  @at-root {
    div[class="container"], div[class$="__container"] {
      #{$h} {
        padding-left: 0;
        padding-right: 0;
      }
    }
  }
}


.blocks {
  //@include flex-container(column, 100px);
  //@include flex-container(column, get-var(space, xl));
  //@include flex-container(column, get-var(space, xl));
  display: flex;
  flex-direction: column;
  @include to-responsive(grid-gap, 30px, 100px);
}

.sub-blocks {
  display: flex;
  flex-direction: column;
  grid-gap: 35px;
}

div[class="container"], div[class$="__container"] {
  @include container;
}

</style>
