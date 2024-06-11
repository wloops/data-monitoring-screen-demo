<script setup>

// 排版方式 分列/分行/独立网格
const layoutModel = 'column' // 'row'|'column'|'grid'
const column = [
  {
    name: 'A01',
    height: 'auto', // 'auto'|'100px'
    direction: 'column', // ''|'row'|'column'
    innerBoxs: [
      {
        name: 'A01-01',
        height: 'auto',
        direction: '',
      },
      {
        name: 'A01-02',
        height: 'auto',
        direction: '',
      }
    ]
  },
  {
    name: 'A01',
    height: 'auto', // 'auto'|'100px'
    direction: 'column', // ''|'row'|'column'
    innerBoxs: [
      {
        name: 'A01-01',
        height: 'auto',
        direction: '',
      },
      {
        name: 'A01-02',
        height: 'auto',
        direction: '',
      }
    ]
  },
  {
    name: 'A02',
    height: 'auto', // 'auto'|'100px'
    direction: 'column', // ''|'row'|'column'
    innerBoxs: [
      {
        name: 'A01-01',
        height: 'auto',
        direction: '',
      },
      {
        name: 'A01-02',
        height: 'auto',
        direction: '',
      },
      {
        name: 'A01-02',
        height: 'auto',
        direction: '',
      }
    ]
  }
]
</script>

<template>
  <div class="main" text-coolGray-300 w-full h-full>
    <div v-if="layoutModel === 'column'" w-full h-full flex flex-row justify-center items-center pl-3 pr-3 pb-3>

      <div v-for="(item, index) in column" :key="index" class="column" w-full h-full flex flex-col justify-center
        items-center m-3>
        <div v-for="(innerBox, innerIndex) in item.innerBoxs" :key="innerIndex" class="innerBox" flex-1 w-full m-3>{{
      innerBox.name }}</div>
      </div>
    </div>
    <div v-else-if="layoutModel === 'row'"></div>
    <div v-else-if="layoutModel === 'grid'"></div>
  </div>
</template>


<style scoped>
.innerBox {
  border: 1px dashed #76c1f3;
}
</style>
