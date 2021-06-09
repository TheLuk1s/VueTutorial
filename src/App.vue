<template>
  <div id="app">
    <CardsGrid />
  </div>
</template>

<script>
import CardsGrid from "./components/CardsGrid";

export default {
  name: "App",
  components: {
    CardsGrid,
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
