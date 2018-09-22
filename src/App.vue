<template>
    <div>
        <div class="demo" @click="attachRed = !attachRed" :class="divClasses"></div>
        <div class="demo"></div>
        <div class="demo"></div>
    </div>
</template>

<script>
export default {
  data: function() {
    return {
      attachRed: false
    };
  },
  computed: {
    divClasses: function() {
      return {
        red: this.attachRed,
        blue: !this.attachRed
      };
    }
  }
};
</script>

<style scoped>
.demo {
  width: 100px;
  height: 100px;
  background-color: gray;
  display: inline-block;
  margin: 10px;
}
.red {
  background-color: red;
}
.blue {
  background-color: blue;
}
</style>
