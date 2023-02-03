<script setup>
import { ref } from 'vue';
const actualShortcut = ref('lightroom');
</script>

<template>
  <div class="container">
    <div class="before-bg" />
    <div class="bg">
      <div class="button-group">
        <button @click="actualShortcut = 'after-effects'">
          <div
            :class="actualShortcut === 'after-effects' ? 'active' : 'disabled'"
          />
          After Effects
        </button>
        <button @click="actualShortcut = 'final-cut-pro'">
          <div
            :class="actualShortcut === 'final-cut-pro' ? 'active' : 'disabled'"
          />
          Final Cut Pro
        </button>
        <button @click="actualShortcut = 'photoshop'">
          <div
            :class="actualShortcut === 'photoshop' ? 'active' : 'disabled'"
          />
          Photoshop
        </button>
        <button @click="actualShortcut = 'lightroom'">
          <div
            :class="actualShortcut === 'lightroom' ? 'active' : 'disabled'"
          />
          Lightroom
        </button>
      </div>
      <img
        :src="'/assets/adobe-' + actualShortcut + '.png'"
        alt="Vue logo"
      />
    </div>
    <div class="after-bg" />
  </div>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: column;
  height: 100vh;
  .before-bg {
    background: linear-gradient(0deg, #323232 0%, #1f1f1f 100%);
    flex: 1;
  }
  .bg {
    display: flex;
    flex-direction: column;
    background: #323232;
    .button-group {
      width: 100%;
      min-width: 900px;
      max-width: 1120px;
      height: 40px;
      margin: -64px 50px 16px auto;
      left: 0;
      right: 0;
      display: flex;
      justify-content: flex-end;
      gap: 8px;
      position: fixed;
      button {
        background: #222222;
        border: 4px solid #0a0c0b;
        border-radius: 4px;
        color: #989596;
        cursor: pointer;
        display: flex;
        align-items: center;
        line-height: 0;
      }
      .active {
        width: 6px;
        height: 6px;
        background: #d4d4d4;
        margin-right: 8px;
        border-radius: 50%;
        margin-bottom: 2px;
      }
      .disabled {
        width: 6px;
        height: 6px;
        background: #0b0b0b;
        margin-right: 8px;
        border-radius: 50%;
        margin-bottom: 2px;
      }
    }
    img {
      flex: 1;
      margin: auto;
      min-width: 740px;
      max-width: 1280px;
      width: 100%;
      flex: 1;
    }
  }
  .after-bg {
    background: linear-gradient(180deg, #323232 0%, #1f1f1f 100%);
    flex: 1;
  }
}
</style>
