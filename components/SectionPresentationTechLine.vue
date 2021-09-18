<template>
  <BaseSection className="presentation">
    <div class="presentation__content">
      <!-- <h2>Российская экосистема печати “Катюша”</h2> -->
      <div class="softwares">
        <div class="softwares__tabs">

        </div>
        <div class="softwares__content">

        </div>
      </div>
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
