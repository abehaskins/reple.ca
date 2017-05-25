<template>
  <div id="navigation">
    <h1>
      <i id="blue">firebase.demo/</i>abeisgreat
    </h1>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style lang="scss">
#navigation {
  background-color: white;
  color: white;
  padding: 10px;

  h1 {
    padding: 0px;
    margin: 0px;
    font-size: 16px;
    font-family: 'Merriweather', serif;
    color: #555;

    i {
      font-style: normal;
      color: #bbb;
    }
  }
}
</style>
