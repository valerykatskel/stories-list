<template>
  <div class="story-popup">
    <div class="story-title">
      <span>{{ storyItem.section }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "StoryPopUp",
  props: {
    storyItem: Object
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss"></style>
