<template>
  <BaseSection className="presentation">
    <div class="presentation__content">
      asdasdasdasd
      <slot>

      </slot>
    </div>
  </BaseSection>
</template>

<script>
export default {
  name: 'SectionPresentation',
  props: {}
}
</script>

<style lang="scss">
.presentation {
  min-height: 642px;
  &__content {
    padding: 30px;
  }
}
</style>
