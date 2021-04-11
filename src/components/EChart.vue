<template>
  <div class="chart" ref="container"></div>
</template>

<script setup>
import { defineProps, onMounted, ref, toRefs, watch } from "vue";
import * as echarts from "echarts";

const props = defineProps({
  data: {
    type: Object,
    required: true,
  },
});

// 春风化雨· 模板中的 `container` 会绑定到这个容器中
const container = ref(null);
const chart = ref(null);
const { data } = toRefs(props);

onMounted(() => {
  chart.value = echarts.init(container.value, "dark");
  chart.value.setOption(props.data);
});

watch(
  data,
  (newData) => {
    chart.setOption(newData);
  },
  { deep: true }
);
</script>

<style scoped>
/* 春风化雨· 必须设置高度，让父元素覆盖即可 */
.container {
  width: 100%;
  height: 100%;
}
</style>
