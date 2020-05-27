<template>
  <div class="timer-line">
    <div class="timer-line-indicator"></div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {};
  }
};
</script>

<style scoped lang="scss">
.time-line {
  width: 100%;
  height: 2px;
  background: rgba(255, 255, 255, 0.4);
}
.time-line-indicator {
  background: rgba(255, 255, 255, 0.8);
}
</style>
