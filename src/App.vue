<template lang='pug'>
  #app
    input(v-model="name")
    p {{ name }}

    a(:href="url") Link <!--v-bind or : es lo mismo -->
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      name: '',

      url: 'https://platzi.com/clases/'
    }
  }
}
</script>

<style lang="scss">
  @import './scss/main.scss'
</style>
