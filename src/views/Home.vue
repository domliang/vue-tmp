<template>
  <div class="home">
    <img width="200" alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your H2O Vue.js App"/>
    <h1>{{ count }}</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import { mapState } from 'vuex'
import { setInterval, clearInterval } from 'timers'

import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  computed: {
    ...mapState({
      count: state => state.count
    })
  },
  mounted () {
    this.intervalTimer = setInterval(() => {
      this.$store.dispatch({
        type: 'increment'
      })
    }, 1000)
  },
  beforeDestroy () {
    clearInterval(this.intervalTimer)
  }
}
</script>
