<template>
  <div id="app">
    <a-menu
      v-model="current"
      mode="horizontal"
    >
      <a-menu-item key="home">
        <router-link to="/">Home</router-link>
      </a-menu-item>
      <a-menu-item key="about">
        <router-link to="/about">About</router-link>
      </a-menu-item>
    </a-menu>
    <div class="pages">
      <router-view/>
    </div>
  </div>
</template>

<style lang="less">
.pages {
  padding-top: 10px;
  text-align: center;
}
</style>

<script>
export default {
  data () {
    return {
      current: ['home']
    }
  }
}
</script>
