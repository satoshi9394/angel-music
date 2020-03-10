<template lang='pug'>
  #app
    section.large
      nav.nav
        .container
          .input-group
            input.form-control(
              type="text"
              placeholder='Buscar Canciones'
              v-model="searchQuery")
            .input-group-append
              a.btn.btn-primary(@click="search") buscar
              a.btn.btn-danger x 
          .container    
            p {{ searchMessage }}    

      .container
        .row
          .col(v-for="t in tracks")
            | {{ t.name }} - {{ t.artists[0].name }}
</template>

<script>
import trackService from './services/track';

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
      if(!this.searchQuery) { return }

      trackService.search(this.searchQuery)
        .then(res => {
          this.tracks = res.tracks.items
        })
    }
  }
}
</script>

<style lang="scss">
  @import './scss/main.scss'
</style>
