<template>
    <div id="exercise">
        <hr>
        <div>
            <button @click="startEffect">Start Effect</button>
            <div id="effect" v-bind:class="effectClasses"></div>
        </div>
        <hr>
        <div v-bind:class="[float, 'blue', 'text-color']">I got no class :(</div>
        <hr>
        <div>
            <input type="text" v-model="userClass">
            <div v-bind:class="[{visible: true}, userClass]"></div>
        </div>
        <hr>
        <div>
            <input type="text" v-model="userClass">
            <input type="text" v-model="isVisible">
            <div v-bind:class="[{visible: isVisible}, userClass]"></div>
        </div>
        <hr>
        <div>
            <input type="text" v-model="myStyle.backgroundColor">
            <div v-bind:style="myStyle"></div>
        </div>
        <hr>
        <div>
            <button v-on:click="startProgress">Start Progress</button>
            <div v-bind:class="['progress-bar']" v-bind:style="progressBar"></div>
        </div>
    </div>
</template>

<script>
  export default {
    data: function () {
      return {
        effectClasses: {
          highlight: false,
          shrink: true
        },
        float: "float",
        userClass: "",
        isVisible: true,
        myStyle: {
          width: "100px",
          height: "150px",
          backgroundColor: "gray"
        },
        progressBar: {
          width: "0px",
          backgroundColor: "red"
        }
      };
    },

    methods: {
      startEffect: function () {
        let vm = this;
        setInterval(function () {
          vm.effectClasses.highlight = !vm.effectClasses.highlight;
          vm.effectClasses.shrink = !vm.effectClasses.shrink;
        }, 1000);
      },
      startProgress: function () {
        let vm = this;
        let width = 0;
        setInterval(function () {
          width = width + 10;
          vm.progressBar.width = width + "px";
        }, 500);
      }
    }
  };
</script>

<style scoped>
    #effect {
        width: 100px;
        height: 100px;
        border: 1px solid black;
    }
    .highlight {
        background-color: red;
        width: 200px !important;
    }
    .shrink {
        background-color: gray;
        width: 50px !important;
    }
    .blue {
        background-color: blue;
    }
    .float {
        float: right;
    }
    .text-color {
        color: yellow;
    }
    .visible {
        width: 100px;
        height: 50px;
    }
    .progress-bar {
        width: 200px;
        height: 20px;
        border: 1px solid black;
    }
</style>
