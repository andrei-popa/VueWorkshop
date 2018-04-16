<template>
  <div>
    <div>Counter: {{ counter }}</div>
    <div>Incremented: {{ counterPlusOne }}</div>
    <div>External counter: {{ ecounter }}</div>
    <br><br>
    <button v-on:click="increment(1)">Increment</button>
    <button v-on:click="increment(-1)">Decrement</button>
    <br>
    <button v-on:click="$emit('change', ecounter + 1)">Increment External</button>
    <button v-on:click="$emit('change', ecounter - 1)">Decrement External</button>
  </div>
</template>

<script>
export default {
  name: 'simple',
  data() { //equivalent of data: function() {}
    return {
      counter: 1
    }
  },
  props: {
    ecounter: {
      type: Number,
      required: true
    }
  },
  computed: {
    counterPlusOne() {
      return this.counter + 1;
    }
  },
  methods: {
    increment(delta) {
      console.log('click', event);
      this.counter = this.counter + delta;
    }
  }
}
</script>
