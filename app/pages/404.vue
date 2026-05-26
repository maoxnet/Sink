<template>
  <div class="container">
    <h1>该商品的活动已结束</h1>
    <p>{{ countdownText }}</p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const countdown = ref(3)
const countdownText = ref('3 秒后自动跳转京东红包领取页面，祝您中大奖！！！')

onMounted(() => {
  const timer = setInterval(() => {
    countdown.value--
    countdownText.value = `${countdown.value} 秒后自动跳转京东红包领取页面，祝您中大奖！！！`
    
    if (countdown.value <= 0) {
      clearInterval(timer)
      window.location.href = 'https://kzurl10.cn/t2z8oz'
    }
  }, 1000)
})
</script>

<style scoped>
.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  color: #333;
}
</style>
