<template lang="pug">
  #app
    img(src="./assets/logo.png")
    h1 PlatziMusic
    ul
      artist-layer(v-for="artist in artists" v-bind:propartist="artist" v-bind:key="artist.mbid")

</template>

<script>
  import getArtists from "./api";
  import ArtistLayer from "./components/Artist";
  export default {
    name: 'app',
      components: {ArtistLayer},
      data () {
      return {
        artists: []
      }
    },
    mounted: function () {
        const self = this;
        getArtists().then(function (artists) { self.artists = artists })
    }
  }
</script>

<style lang="stylus">
  #app
    font-family 'Avenir', Helvetica, Arial, sans-serif
    -webkit-font-smoothing antialiased
    -moz-osx-font-smoothing grayscale
    text-align center
    color #2c3e50
    margin-top 60px
  h1, h2
    font-weight normal
  ul
    list-style-type none
    padding 0
  li
    display inline-block
    margin 0 10px
  a
    color #42b983
</style>
