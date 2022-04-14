<template>
  <div class="holdTwo">
    <TaskNow />
    <Count />
  </div>
</template>

<script>
import TaskNow from "./components/wildFire.vue";
import Count from "./components/counter.vue";

export default {
  name: "App",
  components: {
    TaskNow,
    Count,
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
}

.holdTwo {
  display: flex;
}
</style>
