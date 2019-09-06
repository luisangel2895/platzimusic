<template lang="pug">
  li.artist
    h2: a(:href="propartist.url" target="_blank") {{ propartist.name }}
    img(:src="propartist.image[2]['#text']")
</template>

<script>
  export default {
      name: 'ArtistLayer',
      props: ['propartist']
  }

</script>

<style lang="stylus" scoped>
  li.artist
    display block
    margin 10px 0
</style>
