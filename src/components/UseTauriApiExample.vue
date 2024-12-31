<template>
  <div class="w-full h-full justify-center items-center flex flex-col gap-4">
    <div class="btn" @click="() => {
        getCurrentWebviewWindow().hide()
      }">点我隐藏窗口
    </div>

    <div class="btn" @click="async () => {
      let permissionGranted = await isPermissionGranted()

      if (!permissionGranted) {
        const permission = await requestPermission()
        permissionGranted = permission === 'granted'
      }

      if (permissionGranted) {
        sendNotification({
          title: '这是一个如快插件的通知',
          body: '没错，是的',
        })
      }
    }">点我弹出通知
    </div>
  </div>
</template>

<script setup lang="ts">
import {getCurrentWebviewWindow} from "@tauri-apps/api/webviewWindow";
import {isPermissionGranted, requestPermission, sendNotification} from "@tauri-apps/plugin-notification";
</script>

<style scoped>
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer components {
  .btn {
    @apply w-fit rounded-md px-3 py-1.5 bg-stone-800 cursor-pointer text-stone-50 hover:bg-stone-600 transition;
  }
}
</style>
