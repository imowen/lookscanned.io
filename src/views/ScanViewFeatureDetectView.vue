<template>
  <CanvasScanView v-if="supportCanvasScan" />
  <MagicaScanView v-else />
  <!-- 广告容器 -->
    <div class="ad-container">
      <!-- Google AdSense 代码 -->
      <!-- make PDF like scanned -->
      <ins class="adsbygoogle"
           style="display:block"
           data-ad-client="ca-pub-5638905191417408"
           data-ad-slot="8775002895"
           data-ad-format="auto"
           data-full-width-responsive="true"></ins>
    </div>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue'
import AdComponent from './AdComponent.vue' // 导入广告组件
import { featureDetect } from '@/utils/scan-renderer/canvas-scan'
import CanvasScanView from './CanvasScanView.vue'
import MagicaScanView from './MagicaScanView.vue'

const supportCanvasScan = featureDetect()
  onMounted(() => {
  // 初始化 AdSense
  ;(window.adsbygoogle = window.adsbygoogle || []).push({})
})
</script>
<style scoped>
.scan-view-container {
  display: flex;
  flex-direction: column;
}

.ad-container {
  margin-top: 20px; /* 调整与上方内容的间距 */
  width: 100%;
  /* 其他样式属性 */
}
</style>
