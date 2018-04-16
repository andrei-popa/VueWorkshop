<template>
  <div id="app">
    <img src="./assets/logo.png">
    <Simple :ecounter="counter" @change="changeCounter" />
  </div>
</template>

<script> // an object. Vue creates a component instance here
import Simple from './components/Simple.vue';
// component definition
export default {
  name: 'app',
  components: {
    Simple: Simple //the first one is the name used in the template, the second one is the name used in the file
  },
  data() {
    return {
      counter:0
    }
  },
  methods: {
    changeCounter(newValue) {
      this.counter = newValue;
    }
  }
};
</script>

<style>
/* the style is globally here */
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
/* <style scope ..> is local for a specified component */
</style>
