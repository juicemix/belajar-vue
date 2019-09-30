<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>{{ test }}</h3>
    <test_component v-bind:haha="test"></test_component>
    <button v-on:click="cobaclick">COBA</button>
  </div>
</template>

<script>
import test_component from './test_component'
export default {
  name: 'HelloWorld',
  data : function () {
    return {
      test: "test",
      angka: 5
    }
  },
  props: {
    msg: String
  },
  methods: {
    cobaclick: function() {
      this.test = "BERUBAH"
    }
  },
  components: {
    test_component
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
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
