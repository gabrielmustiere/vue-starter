<template>
  <div>
   <button v-on:click="increase(2, $event)">Cliquer</button>
   <button v-on:click="counter++">Cliquer</button>
    <p>{{ counter * 2 > 10 ? 'Plus de 10' : 'Moins de 10'}}</p>
    <p v-on:mousemove="updateCoordinates">
        Coorrdinates : {{ x }} / {{ y }}
        - <span v-on:mousemove.stop>DEAD SPOT</span>
    </p>
      <input type="text" v-on:keyup.enter.space="alert" title="">
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      counter: 0,
      x: 0,
      y: 0
    };
  },
  methods: {
    increase: function(step, event) {
      console.log(event);
      this.counter += step;
    },
    updateCoordinates: function(event) {
      this.x = event.clientX;
      this.y = event.clientY;
    },
    alert: function(event) {
      console.log(event);
    }
  }
};
</script>
