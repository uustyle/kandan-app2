<template>
  <div class="hello">
{{ info }}
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
<a href="#" v-scroll-to="'#element'">Scroll to #element</a>
<input type="button" v-on:click="move()" value="move" />

<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>
<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>

      <div id="element">
      Hi. I'm #element.
      </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App32',
      info: null
    }
  },
  mounted () {
    // axios
    //   .post('/auth/login')
    //   .then(response => (this.info = response))
  },

  methods: {

    move() {
var cancelScroll = VueScrollTo.scrollTo("#element")

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
