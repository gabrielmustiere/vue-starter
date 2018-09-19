<template>
  <div>
    <h1>{{ title }}</h1>
    <h2>{{ sayTtitle() }}</h2>
    <hr>
    <a :href="link">Google</a>
  </div>
</template>

<script>
export default {
  template: "",
  data: function() {
    return {
      title: "VueJS Starter",
      helloWorld: "Hello world :)",
      link: "http://wwww.google.fr"
    };
  },
  methods: {
    sayTtitle: function() {
      return this.helloWorld;
    }
  }
};
</script>
