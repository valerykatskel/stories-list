<template>
  <div id="app">
    <div class="stories-wrapper">
      <ul
        class="stories-list"
        :width="getFullWidth"
        :style="{ width: getFullWidth + 'px' }"
      >
        <li
          v-for="(story, id) in stories"
          :key="story.id"
          :class="{ new: story.viewedDate > 0 }"
        >
          <story-item
            :item-id="id"
            :story-item="story"
            @on-click="onClickStory"
          />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import StoryItem from "@/components/StoryItem";
export default {
  name: "App",
  components: {
    StoryItem
  },
  data() {
    return {
      storiesWidth: 3,
      stories: [
        {
          title: "Story #1",
          viewedDate: 0,
          publishDate: 1590598650,
          image:
            "https://dh.img.tyt.by/552x368c/n/reuters/09/10/turciya_otdykh_reuters_rtr1tikc.jpg",
          slides: [
            {
              type: "video",
              url:
                "https://dh.img.tyt.by/news/special/stories/stop_oduvanchik_voda_02.mp4",
              title: "На торгах 13 июля доллар и евро подешевели",
              subtitle: "Доллар снизился на BYN 0,0115 — до 2,4185 рубля"
            }
          ]
        },

        {
          title: "Story #2",
          viewedDate: 0,
          publishDate: 1590598640,
          image:
            "https://img.tyt.by/n/afisha/08/9/seafoodbar_by_john_dory_take_away.jpg",
          slides: []
        },

        {
          title: "Story #3",
          viewedDate: 0,
          publishDate: 1590598550,
          image:
            "https://dh.img.tyt.by/720x720s/n/zamirovskiy/0e/7/05_dezinfekciya_transporta_koronavirus_20200401_zam_tutby_phsl.jpg",
          slides: []
        },
        {
          title: "Story #4",
          viewedDate: 0,
          publishDate: 1590598450,
          image:
            "https://dh.img.tyt.by/720x720s/n/ekonomika/0a/f/dengi_pensiya_zarplata_monety_valyuta_rubl.jpg",
          slides: []
        },
        {
          title: "Story #5",
          viewedDate: 1590598730,
          publishDate: 1590598350,
          image:
            "https://dh.img.tyt.by/720x720s/n/06/f/trump_tramp_27042020.jpg",
          slides: []
        },
        {
          title: "Story #6",
          viewedDate: 0,
          publishDate: 1590598320,
          image:
            "https://dh.img.tyt.by/552x368c/n/reuters/09/10/turciya_otdykh_reuters_rtr1tikc.jpg",
          slides: []
        },

        {
          title: "Story #7",
          viewedDate: 0,
          publishDate: 1590598300,
          image:
            "https://img.tyt.by/n/afisha/08/9/seafoodbar_by_john_dory_take_away.jpg",
          slides: []
        },

        {
          title: "Story #8",
          viewedDate: 1590598790,
          publishDate: 1590598250,
          image:
            "https://dh.img.tyt.by/720x720s/n/zamirovskiy/0e/7/05_dezinfekciya_transporta_koronavirus_20200401_zam_tutby_phsl.jpg",
          slides: []
        },
        {
          title: "Story #9",
          viewedDate: 1590598800,
          publishDate: 1590598220,
          image:
            "https://dh.img.tyt.by/720x720s/n/ekonomika/0a/f/dengi_pensiya_zarplata_monety_valyuta_rubl.jpg",
          slides: []
        },
        {
          title: "Story #10",
          viewedDate: 1590598750,
          publishDate: 1590598180,
          image:
            "https://dh.img.tyt.by/720x720s/n/06/f/trump_tramp_27042020.jpg",
          slides: []
        }
      ]
    };
  },
  methods: {
    getTimestamp: datetime => {
      const dt = datetime.split(".");

      console.log(dt);
      return new Date(`${datetime} 00:00:00`).getTime() / 1000;
    },
    onClickStory: function(item) {
      this.stories.forEach((el, id) => {
        if (id === item.id) {
          el.viewedDate = Date.now();
        }
      });
    }
  },
  mounted() {
    this.storiesWidth = this.stories.length * 90;
  },
  computed: {
    getFullWidth: function() {
      return this.storiesWidth;
    }
  }
};
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.stories-wrapper {
  overflow: auto;
}
.stories-list {
  list-style-type: none;
  padding: 0;
  margin: 0 0 10px 0;
  li {
    display: inline-block;
    cursor: pointer;

    img {
      border: 2px solid #ff5555;
      box-sizing: border-box;
    }
    &.new {
      img {
        border-color: transparent;
      }
    }
  }
}
</style>
