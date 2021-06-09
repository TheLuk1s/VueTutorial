<template>
  <div id="app">
    <Card
      name="vardas"
      link="https://www.google.com/"
      :tweets="3"
      :following="1001"
    />
  </div>
</template>

<script>
import Card from "./components/Card";

export default {
  name: "App",
  components: {
    Card,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  justify-content: center;
}
</style>
