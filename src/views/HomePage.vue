<template>
  <h1>{{  h1  }}</h1>
  <div>
    <TButton :label="btn1" />
    <TButton :label="btn2" />
  </div>
</template>

<script>

import TButton from '@/components/TButton.vue'
import lang from '@/lang/lang.js'
export default {
  name: 'HomePage',
  props: {
    lang: String
  },
  created () {
    this.labels = lang.filter(obj => obj.page = 'HomePage')
  },
  data () {
    return {
      labels: []
    }
  },
  computed: {
    h1 () {
      return this.labels.find(obj => obj.label === 'h1')[this.lang]
    },
    btn1 () {
      return this.labels.find(obj => obj.label === 'btn1label')[this.lang]
    },
    btn2 () {
      return this.labels.find(obj => obj.label === 'btn2label')[this.lang]
    }
  },
  components: { TButton }
}

</script>