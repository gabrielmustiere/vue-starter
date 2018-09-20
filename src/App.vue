<template>
  <div>
   <button v-on:click="increase">Cliquer</button>
    <p>{{counter}}</p>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      counter: 0
    };
  },
    methods : {
      increase : function(){
          this.counter++;
      }
    }
};
</script>
