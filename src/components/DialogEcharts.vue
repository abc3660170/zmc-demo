<script setup lang="ts">
import * as echarts from 'echarts';
import { nextTick, ref, watch } from 'vue';
const dialogVisible = ref(false);
watch(dialogVisible, (val) => {
  if (!val) {
    return false;
  }
  nextTick(() => {
    const myChart = echarts.init(document.querySelector('.chart') as HTMLElement);
    myChart.setOption({
      title: {
        text: 'ECharts 入门示例'
      },
      tooltip: {},
      xAxis: {
        data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
      },
      yAxis: {},
      series: [
        {
          name: '销量',
          type: 'bar',
          data: [5, 20, 36, 10, 10, 20]
        }
      ]
    });
  })

})


</script>

<template>
  <div>
    <el-button type="text" @click="dialogVisible = true">点击打开 Echart图表</el-button>
    <el-dialog title="提示" :visible.sync="dialogVisible" width="30%">
      <div class="chart" style="width: 100%; height: 400px;"></div>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
  </div>
</template>
