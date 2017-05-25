<template>
  <div id="app">
    <navigation></navigation>
    <profile></profile>
    <div class="copyright">
      by <a href="https://abe.today/share/twitter">@abeisgreat</a>
    </div>
  </div>
</template>

<script>
import Navigation from './Navigation.vue'
import Profile from './Profile.vue'

export default {
  name: 'app',
  components: {Navigation, Profile},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;

  .copyright {
    clear: both;
    float: left;
    width: 100%;

    border-top: 1px solid #eee;
    margin-top: 30px;

    padding-top: 20px;
    text-align: center;
    font-size: 14px;
    color: #ccc;

    a {
      color: #aaa;
      text-decoration: none;
    }
  }
}
</style>
