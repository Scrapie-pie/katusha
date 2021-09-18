<template>
  <component :is="icon" :class="`icon icon_${icon}`"/>
</template>

<script>
let names = require('~/src/icons/names.json');
import '~/src/icons/style.css';

export default {
  name: 'Icon',
  props: {
    icon: {
      type: String,
      required: true
    }
  },
  components: {
    ...Object.fromEntries(names.map(name => {
      return [
        name,
        () => import(`~/src/icons/${name}.svg`)
      ]
    }))
  },
};
</script>

<style lang="scss">

</style>
