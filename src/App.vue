<script setup lang="ts">
import DialogEcharts from './components/DialogEcharts.vue'
import PromiseDemo from "./components/PromiseDemo.vue";
</script>
<template>
  <div>
    <DialogEcharts />
    <div class="divide"></div>
    <PromiseDemo />
  </div>
</template>
<style scoped>
.divide {
  margin: 30px 0;
  &::after {
    content: '------------ 分割线 ------------';
  }
}
</style>


