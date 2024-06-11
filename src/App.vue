<script setup>
import { RouterView } from 'vue-router'
import autofit from 'autofit.js'
onMounted(() => {
  autofit.init({
    dh: 1080,
    dw: 1920,
    // scale: 1.2,
    // width: "80%",
    // height: "100%",
    el: '#app',
    resize: true,
  })
})
</script>

<template>
  <!-- 加载动画 -->
  <!-- <div id="load">
    <div class="load_img">
      <img class="jzxz1" src="./assets/images/jzxz1.png" />
      <img class="jzxz2" src="./assets/images/jzxz2.png" />
    </div>
  </div> -->
  <div style="width: 100%; position: absolute; top: 10%; left: 0">
    <div class="map">
      <div class="map1"></div>
      <!-- 地图模块 -->
      <div class="map2"></div>
      <div class="map3"></div>
    </div>
  </div>
  <RouterView />
</template>

<style lang="scss" scoped>

/* 加载旋转动画 */
#load {
  width: 100%;
  height: 100%;
  position: absolute;
  background: url(./assets/images/bg.jpg) no-repeat transparent;
  background-size: cover;
  top: 0;
  left: 0;
  z-index: 999;
}

#load .load_img {
  position: absolute;
  left: calc(50% - 182px);
  top: calc(50% - 182px);
}

.load_img img {
  position: absolute;
  left: 0;
  top: 0;
}

.load_img .jzxz1 {
  animation: xz1 8s infinite linear;
}

@keyframes xz1 {
  from {
    transform: rotate(0deg);
  }

  50% {
    transform: rotate(180deg);
  }

  to {
    transform: rotate(360deg);
  }
}

.load_img .jzxz2 {
  animation: xz2 7s infinite linear;
}

@keyframes xz2 {
  from {
    transform: rotate(0deg);
  }

  50% {
    transform: rotate(-180deg);
  }

  to {
    transform: rotate(-360deg);
  }
}

.map {
  position: relative;
  top: 0;
  height: 850px;

  .map1 {
    width: 480px;
    height: 480px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: url(./assets/images/map.png);
    background-size: 100% 100%;
    opacity: 0.3;
  }

  .map2 {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 560px;
    height: 560px;
    background: url(./assets/images/lbx.png);
    animation: rotate1 15s linear infinite;
    opacity: 0.6;
    background-size: 100% 100%;
  }

  .map3 {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 600px;
    height: 600px;
    background: url(./assets/images/jt.png);
    animation: rotate2 10s linear infinite;
    opacity: 0.6;
    background-size: 100% 100%;
  }

  .chart {
    position: absolute;
    top: 0;
    left: 0;
    /* // background-color: pink; */
    width: 100%;
    height: 10.125rem;
  }

  @keyframes rotate1 {
    from {
      transform: translate(-50%, -50%) rotate(0deg);
    }

    to {
      transform: translate(-50%, -50%) rotate(360deg);
    }
  }

  @keyframes rotate2 {
    from {
      transform: translate(-50%, -50%) rotate(0deg);
    }

    to {
      transform: translate(-50%, -50%) rotate(-360deg);
    }
  }
}
</style>
