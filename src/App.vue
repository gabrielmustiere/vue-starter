<template>
    <div>
        <button v-on:click="increase">Cliquer</button>
        <p>Counter : {{ counter }}</p>
        <p>Result : {{ result }}</p>

    </div>
</template>

<script>
    export default {
        data: function () {
            return {
                counter: 0,
                result: ""
            };
        },
        methods: {
            increase: function () {
                this.counter++;
                this.result = this.counter > 5 ? "Plus grand que 5" : "Plus petit que 5";
            }
        }
    };
</script>
