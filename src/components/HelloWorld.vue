<template>
  <div class="hello">
    <button v-on:click="toggleText()">ToogleText</button>
    <button v-on:click="toggleInput()">ToogleInput</button>
    <button v-on:click="reverseTextMethod()">reverseText</button>
    <p v-if="showText">{{ msg | reverse }}</p>
    <p>{{ reverseText }}</p>
    <ul>
      <li v-for="user in users" v-bind:key="user" v-on:click="$emit('clickUser', user)">
        {{ user }}
      </li>
    </ul>
    <input v-if="showInput" type="text" v-model="msg"/>
    <h1>{{ msg }}</h1>
    <h2>{{ text }}</h2>
    <Mio/>
  </div>
</template>

<script>
import Mio from './Mio'

export default {
  props: ['users'],
  name: 'HelloWorld',
  data () {
    return {
      text: 'Hola de nuevo',
      showText: false,
      msg: 'Mi Primera App con VUE <3',
      showInput: true
    }
  },
  components: {
    Mio
  },
  methods: {
    toggleText: function () {
      this.showText = !this.showText
    },
    reverseTextMethod: function () {
      this.text = this.text
        .split('')
        .reverse()
        .join('')
    },
    toggleInput: function () {
      this.showInput = !this.showInput
    }
  },
  computed: {
    reverseText: function () {
      return this.text
        .split('')
        .reverse()
        .join('')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
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
