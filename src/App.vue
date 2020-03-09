<template lang='pug'>
  #app
    p(v-show="showValue") {{ value }}<!--sirve para poner la propiedad none de display-->
    p(v-if="showValue") {{ value }}<!--si es false ni siquiera lo crea en el dom-->
    p(v-else-if="false") {{ 'algo mas' }}
    p(v-else) {{ 'lo ultimo' }}

    ul
      li(v-for="item in items") {{ item }}
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Hello word!',

      showValue: false,
      value: 'algo',

      items: [1, 2, 3, 4, 5]
    }
  }
}
</script>

<style lang="scss">
  @import './scss/main.scss'
</style>
