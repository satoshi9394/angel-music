<template lang='pug'>
  #app
    section.large
      nav.navbar
        .container
          .input-group
            input.form-control(
              type="text"
              placeholder='Buscar Canciones'
              v-model="searchQuery")
            .input-group-append
              a.btn.btn-primary(@click="search") buscar
              a.btn.btn-danger x
            p {{ searchMessage }}
      .container
        .row
          .col(v-for="t in tracks") {{ t.name }} - {{ t.artis }}
</template>

<script>
const tracks = [
  { name: 'muchacha', artis: 'luis alberto' },
  { name: 'hoy aca en el baile', artis: 'el pepo' },
  { name: 'i was made for loving', artis: 'kiss' }]

export default {
  name: 'app',
  data () {
    return {
      searchQuery: '',
      tracks: []
    }
  },

  computed: {
    searchMessage () {
      return `Encontrados: ${this.tracks.length}`
    }
  },

  methods: {
    search () {
      this.tracks = tracks
    }
  }
}
</script>

<style lang="scss">
  @import './scss/main.scss'
</style>
