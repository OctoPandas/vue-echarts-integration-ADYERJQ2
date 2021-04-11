<template>
  <EChart :data="barChartData()" />
</template>

<script setup>
import EChart from './EChart.vue'
import barChartData from '../charts/barChartData'
</script>
