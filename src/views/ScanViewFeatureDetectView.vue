<template>
  <CanvasScanView v-if="supportCanvasScan" />
  <MagicaScanView v-else />
  <!-- 在适当的位置添加广告组件 -->
  <AdComponent class="ad-container" />
</template>

<script lang="ts" setup>
  import AdComponent from './AdComponent.vue' // 导入广告组件
import { featureDetect } from '@/utils/scan-renderer/canvas-scan'
import CanvasScanView from './CanvasScanView.vue'
import MagicaScanView from './MagicaScanView.vue'

const supportCanvasScan = featureDetect()
</script>
<style scoped>
.ad-container {
  /* 设置广告容器的样式 */
  margin-top: 20px;
  width: 100%;
  /* 其他样式属性 */
}
</style>
