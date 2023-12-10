<template>
  <div class="histogram" id="histogram"></div>
</template>
<script setup>
import * as echarts from 'echarts'
import { onMounted } from 'vue'

const init = () => {
  // 基于准备好的dom，初始化echarts实例
  var myChart = echarts.init(document.getElementById('histogram'))
  // 绘制图表
  myChart.setOption({
    title: {
      text: 'ECharts 入门示例'
    },
    tooltip: {},
    xAxis: {
      type: 'category', //类目轴
      data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
    },
    yAxis: {
      type: 'value' //数值轴
    },
    series: [
      {
        name: '销量',
        type: 'bar',
        data: [5, 20, 36, 10, 10, 20]
      }
    ]
  })
}

onMounted(() => {
  init()
})
</script>
<style scoped>
.histogram {
  width: 500px;
  height: 500px;
}
</style>
