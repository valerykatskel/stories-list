<template>
  <div class="story" @click="clickStory(storyItem)">
    <img :src="storyItem.image" />
    <div class="story-title">
      <span>{{ storyItem.section }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "StoryItem",
  props: {
    storyItem: Object
  },
  methods: {
    clickStory: function(item) {
      const params = {
        item: item
      };
      //this.$emit("on-click", params);
      this.$emit("on-click", params);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
img {
  width: 60px;
  height: 60px;
  border-radius: 50%;
}
.story {
  width: 90px;
  height: 80px;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;

  .story-title {
    margin-top: 5px;
    width: 90px;
    overflow: hidden;
    text-overflow: ellipsis;
    box-sizing: border-box;
    padding: 0 5px;
  }

  span {
    font-size: 11px;
    line-height: 15px;
    white-space: nowrap;
  }
}
</style>
