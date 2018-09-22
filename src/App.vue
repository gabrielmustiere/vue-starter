<template>
    <div>
        <div class="demo" @click="attachRed = !attachRed" :class="divClasses"></div>
        <div class="demo" :class="[color,{red:attachRed}]"></div>
        <div class="demo" :class="color"></div>
        <hr>
        <input type="text" v-model="color">
    </div>
</template>

<script>
export default {
  data: function() {
    return {
      attachRed: false,
      color: "green"
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

.green {
  background-color: green;
}
</style>
