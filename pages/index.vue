<template>
  <main>
    <SectionIntro
      title="Экосистема корпоративной печати"
      description="Российские разработчики программного обеспечения и производитель печатного оборудования, в том числе внешних терминалов авторизации"
      :hasDemo="true"
    />
    <!-- <SectionPresentation/> -->
    <div>
      <Icon icon="test"/>
    </div>

    <SectionSkills/>
    <VVideo></VVideo>
    <SectionInvite/>
    <!-- <SectionContactUs/> -->
  </main>
</template>

<style lang="scss">
main {
  padding-top: 60px;
  padding-bottom: 140px;
}

section div[class*="__container"] {
  @include container;
}

</style>
