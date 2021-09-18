<template>
  <input
    class="input"
    :type="this.type"
    :value="this.value"
    @input="$emit('input', $event.target.value)"
  />
</template>

<script>
export default {
  name: 'BaseInput',
  props: {
    type: {
      type: String,
      default: 'text',
      // validator: function (value) {
      //   return ['text', 'password'].includes(value);
      // }
    },
    // required: Boolean,
    value: String,
  },
}
</script>

<style lang="scss">
.input {
  font-family: inherit;
  font-size: inherit;
  font-weight: inherit;
  color: currentColor;
  outline: none;
  padding: 0;
  border: none;



  &[type="text"], &[type="password"] {
    background-color: transparent;
    width: 100%;
    height: 100%;
    cursor: text;
  }
}
</style>
