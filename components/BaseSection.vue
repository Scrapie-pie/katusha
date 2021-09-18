<template>
  <section :class="'section' + this.classNames">
    <div class="container">
      <slot></slot>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BaseSection',
  props: {
    className: String,
  },
  computed: {
    classNames() {
       return ' ' + this.className;
    },
  }
}
</script>

<style lang="scss">
.section {
  &__wrapper {
    @include container;
  }
}
</style>
