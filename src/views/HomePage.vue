<script setup>
import BusinessOperation from '@/views/Business-operation/index.vue'
// import DeviceStatus from '@/views/device-status/index.vue'
// import DeviceRunStatus from '@/views/device-run-status/index.vue'


const parentData = ref(null) // 父组件传过来的数据，默认为空
const currentTab = ref('BusinessOperation')
const tabs = {
  BusinessOperation,
  // DeviceStatus,
  // DeviceRunStatus,
}

const componentKey = ref(0);

function refreshComponent() {
  // 改变key来强制重新渲染组件
  componentKey.value++;
}
</script>
<template>
  <div w-full h-full>
    <div class="app-header borde-dashed">
      <header-component @selectTab="currentTab = $event" :currentTab="currentTab"
        @refreshComponent="refreshComponent"></header-component>
    </div>
    <div class="app-content borde-dashed">
      <!-- 页面主体部分 -->
      <component :is="tabs[currentTab]" :parentData="parentData" :key="componentKey"
        @refreshComponent="refreshComponent"></component>
    </div>
  </div>
</template>
<style scoped>
/* @import '../styles/index.scss'; */
.app-header {
  height: 90px;
}

.app-content {
  height: calc(100% - 90px);
}
</style>
