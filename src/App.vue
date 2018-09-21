<template>
    <div>
        <button v-on:click="counter++">Increase</button>
        <button v-on:click="counter--">Decrease</button>
        <button v-on:click="secondCounter++">Increase Second</button>
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
      console.log("Computed");
      return this.counter > 5 ? "Plus grand que 5" : "Plus petit que 5";
    }
  },
  methods: {
    result: function() {
      console.log("Methods");
      return this.counter > 5 ? "Plus grand que 5" : "Plus petit que 5";
    }
  },
  watch: {
    counter: function(value) {
      var vm = this;
      setTimeout(function() {
        vm.counter = 0;
      }, 2000);
    }
  }
};
</script>
