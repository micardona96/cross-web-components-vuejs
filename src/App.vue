<template>
  <div id="app">
    <Label></Label>
    <Button></Button>
  </div>
</template>

<script>
import Button from "./components/Button.vue";
import Label from "./components/Label.vue";

export default {
  name: "App",
  components: {
    Label,
    Button,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
