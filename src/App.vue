<template>
  <button v-if="lang !== 'sk'" @click="lang = 'sk'">sk</button>
  <button v-if="lang !== 'en'" @click="lang = 'en'">en</button>
  <HomePage :lang="lang" />
  <input type="submit">
</template>


<script>
import HomePage from './views/HomePage.vue'
export default {
  name: 'App',
  data () {
    return {
      lang: 'sk'
    }
  },
  components: { HomePage }
}

</script>

<style lang="styl" scoped>

@import 'variables.styl'

button
  background: lighten($primary, 20)


</style>

