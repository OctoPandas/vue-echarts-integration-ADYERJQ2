<template>
    <BarChart class="bar-chart"/>
</template>

<script setup>
import BarChart from './components/BarChart.vue'
</script>

<style>
body {
  margin: 0;
  background: hsl(210deg, 20%, 10%);
}
#app {
  width: 100vw;
  height: 100vh;
  display: grid;
  /* 如果这里写成 place-content: center，那么图片默认的高度为 0，原因未知 */
  place-items: center;
}

</style>

<style scoped>
.bar-chart {
  width: 50%;
  height: 70%;
}
</style>
