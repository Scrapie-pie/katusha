<template>
  <a :href="href" class="contact" v-once>
    <Icon :icon="icon"/>
    {{value}}
  </a>
</template>

<script>
export default {
  name: 'BaseContact',
  props: {
    value: {
      type: String,
      required: true,
      validator: (value) => !!determineType(value)
    }
  },
  computed: {
    type() {
      return determineType(this.value);
    },
    href() {
      return this.type === 'email' ?
        `mailto:${this.value}` :
        `tel:${formatTel(this.value)}`;
    },
    icon() {
      return this.type === 'email' ?
        'email' :
        'tel';
    },
  },
}

function formatTel(value) {
  return value.replace(/[\(|\)|-|\s]/g, '');
}

function determineType(value) {
  let isEmail = /^[\w|\d|-]+@[\w|\d|-]+\.\w+$/.test(value);
  let isTel = !formatTel(value)
    .replace(/^\+/, '')
    .split('')
    .map(x => x == 0 ? 0 : (parseInt(x) || x))
    .filter(char => typeof(char) !== 'number')
    .length;

  if (isEmail) {
    return 'email';
  } else if (isTel) {
    return 'tel';
  }
}
</script>

<style lang="scss">
.contact {
  @include flex-container(row, .45em);
  align-items: center;

  .icon {
    //color: get-variable(color, light);
  }

  &:hover {
    .icon {
      color: currentColor !important;
    }
  }
}
</style>
