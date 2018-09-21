<template>
    <div>
        <button @click="counter++">Increase</button>
        <button @click="counter--">Decrease</button>
        <button @click="secondCounter++">Increase Second</button>
        <p>Counter : {{ counter }} | {{ secondCounter }}</p>
        <p>Result : {{ result() }} | {{ output }}</p>

    </div>
</template>

<script>
export default {
  data: function() {
    return {
      counter: 0,
      secondCounter: 0
    };
  },
  computed: {
    output: function() {
      return this.counter > 5 ? "Plus grand que 5" : "Plus petit que 5";
    }
  },
  methods: {
    result: function() {
      return this.counter > 5 ? "Plus grand que 5" : "Plus petit que 5";
    }
  },
  watch: {
    counter: function() {
      let vm = this;
      setTimeout(function() {
        vm.counter = 0;
      }, 2000);
    }
  }
};
</script>
