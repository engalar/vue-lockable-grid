<template>

<div>

    <div>
      <md-progress md-indeterminate></md-progress>
<md-progress class="md-accent" md-indeterminate></md-progress>
<md-progress class="md-warn" md-indeterminate></md-progress>

<form novalidate @submit.stop.prevent="open">
  <div>
    <div class="md-body-2">Vertical</div>
    <md-radio v-model="vertical" id="top" name="snackbar-vertical" md-value="top">top</md-radio>
    <md-radio v-model="vertical" id="bottom" name="snackbar-vertical" md-value="bottom">bottom</md-radio>
  </div>

  <div>
    <div class="md-body-2">Horizontal</div>
    <md-radio v-model="horizontal" id="left" name="snackbar-horizontal" md-value="left">left</md-radio>
    <md-radio v-model="horizontal" id="center" name="snackbar-horizontal" md-value="center">center</md-radio>
    <md-radio v-model="horizontal" id="right" name="snackbar-horizontal" md-value="right">right</md-radio>
  </div>

  <div>
    <div class="md-body-2">Delay</div>

    <md-input-container>
      <md-input type="number" v-model="duration"></md-input>
    </md-input-container>
  </div>

  <md-button type="submit" class="md-primary md-raised">Open Snackbar</md-button>

  <md-snackbar :md-position="vertical + ' ' + horizontal" ref="snackbar" :md-duration="duration">
    <span>Connection timeout. Showing limited messages.</span>
    <md-button class="md-accent" md-theme="light-blue" @click.native="$refs.snackbar.close()">Retry</md-button>
  </md-snackbar>
</form>


    </div>

    <h1>{{ msg }}</h1>

    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'world',
  data () {
    return {
      msg: 'Welcome to World!',
      vertical: 'bottom',
      horizontal: 'center',
      duration: 4000
    }
  },
  methods: {
    open () {
      this.$refs.snackbar.open()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
