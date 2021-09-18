<template>
  <button class="button">
    <Icon v-if="this.icon" :icon="this.icon"/>
    <slot></slot>
    </span>
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    icon: String,
  }
}
</script>

<style lang="scss">
.button {
  cursor: pointer;
  border: none;
  border-radius: 4px;

  padding: get-variable(space, micro-sm) 35px;

  height: 50px;

  //display: flex;
  display: inline-flex;
  align-items: center;
  justify-content: space-between;

  background-color: get-variable(color, blue);
  box-shadow: 0px 4px 16px rgba(0, 141, 210, 0.15); // cscs function hex opacity
  color: get-variable(color, white);

  font-family: inherit;
  line-height: 1em;
  font-size: 20px;
  letter-spacing: 0.04em;

  width: 100%;

  font-size: 20px;
  // &__label {
  //
  //   //font-weight: 500;
  // }
  max-width: fit-content;

  gap: 15px;

  &:active {
    box-shadow: 0px 0px 5px rgb(0 0 0 / 30%) inset;
  }

  &_inline {
    display: inline-flex;
  }
}
</style>
