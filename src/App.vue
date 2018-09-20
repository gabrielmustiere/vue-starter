<template>
  <div>
   <button v-on:click="increase">Cliquer</button>
    <p>{{counter}}</p>
    <p v-on:mousemove="updateCoordinates">Coorrdinates : {{ x }} / {{ y }}</p>
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
    increase: function() {
      this.counter++;
    },
      updateCoordinates : function(event){
        this.x = event.clientX;
        this.y = event.clientY;
      }
  }
};
</script>
