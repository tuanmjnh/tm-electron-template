<script setup lang="ts">
const onOpenWindowChrome = (message: any) => {
  // Send information to the main process
  // if a listener has been set, then the main process
  // will react to the request !
  window.electron.ipcRenderer.send('window-chrome', { sync: true })
}
const onOpenSeleniumChrome = (message: any) => {
  window.electron.ipcRenderer.send('selenium-chrome', { sync: true })
}
</script>
<template>
  <el-row class="mb-4">
    <el-button type="primary" @click="onOpenWindowChrome">Open Window Chrome</el-button>
    <el-button type="success" @click="onOpenSeleniumChrome">Open Selenium Chrome</el-button>
    <!-- <el-button type="info" @click="onDialogSaveFile">Save File Dialog</el-button> -->
    <!-- <el-button type="warning">Warning</el-button> -->
    <!-- <el-button type="danger">Danger</el-button> -->
  </el-row>
</template>
<style scoped></style>
