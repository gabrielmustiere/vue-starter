<template>
    <div>
        <div class="demo" :style="myStyle"></div>
        <div class="demo" :style="myStyle"></div>
        <div class="demo" :style="myStyle"></div>
        <hr>
        <input type="text" v-model="color" @change="color">
        <input type="text" v-model="size">
    </div>
</template>

<script>
  export default {
    data: function () {
      return {
        color: "gray",
        size: 10,
        unity : 'rem'
      };
    },
    computed: {
      myStyle: function () {
        return {
          backgroundColor: this.color,
          width: this.size + this.unity,
          height: this.size + this.unity
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
