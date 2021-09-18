<template>
  <label class="field" @input="this.showPlaceholder">
    <div class="field__wrapper">
      <div class="field__content">
        <BaseInput
        v-bind="this.$attrs"
        />
        <span
          v-if="this.placeholder"
          v-show="this.shownPlaceholder"
          class="field__placeholder">
          {{placeholder}}
        </span>
      </div>
    </div>
  </label>
</template>

<script>
export default {
  name: 'BaseField',
  inheritAttrs: false,
  props: {
    placeholder: String,
  },
  data: () => ({
    shownPlaceholder: true,
  }),
  methods: {
    showPlaceholder(event) {
       this.shownPlaceholder = !event.target.value.length;
    }
  }
}
</script>

<style lang="scss">
.field {
  $field: &;

  width: 100%;
  display: flex;
  flex-direction: column;

  &__wrapper {
    cursor: text;
    background-color: get-variable(color, white);
    box-shadow: 0px 2px 10px rgb(0 0 0 / 5%);
    position: relative;
    border-left: 3px solid get-variable(color, blue);



    display: flex;
    align-items: center;
    height: 50px;

    padding: 10px 25px;
    width: 100%;

    font-size: 20px;
    font-weight: 300;
  }

  &__content {
    width: 100%;
    height: 100%;
    overflow: hidden;
    position: relative;
  }

  &__placeholder {
    cursor: text;
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
  }

  .input {
    // &:focus + #{$field}__placeholder {
    //   display: none;
    // }
    &[required] + #{$field}__placeholder {
      &:after {
        content: ' *';
        color: get-variable(color, blue);
      }
    }
  }

}
</style>
