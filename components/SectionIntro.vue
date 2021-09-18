<template>
  <BaseSection className="intro"> <!-- replace class prop on something -->
    <h1 v-if="this.title">
      {{title}}
    </h1>
    <div v-if="this.description" class="intro__description">
      {{description}}
    </div>
    <BaseButton
      v-if="this.hasDemo"
      icon="airpay">
      Посетить демо зал
    </BaseButton>
  </BaseSection>
</template>

<script>
export default {
  name: 'SectionIntro',
  props: {
    title: String,
    description: String,
    hasDemo: Boolean,
  }
}
</script>

<style lang="scss">
.intro {
  &__description {
    @include h(3, get-variable(color, grey_dark));
    margin-bottom: 72px;
  }
  .button {
    //margin-bottom: 30px;
  }
  margin-bottom: 30px;
}
</style>
