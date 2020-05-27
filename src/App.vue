<template>
  <div id="app">
    <div class="stories-wrapper">
      <ul
        class="stories-list"
        :width="getFullWidth"
        :style="{ width: getFullWidth + 'px' }"
      >
        <li
          v-for="story in stories"
          :key="story.id"
          :class="{ viewed: !story.viewedDate }"
        >
          <story-item :story-item="story" />
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
          title:
            "Турция и Черногория — возможно, Украина — пока нет. Куда белорусы смогут поехать на отдых этим летом",
          section: "Новость дня",
          viewedDate: 1590598820,
          publishDate: 1590598650,
          image:
            "https://dh.img.tyt.by/552x368c/n/reuters/09/10/turciya_otdykh_reuters_rtr1tikc.jpg"
        },

        {
          title:
            "Вот что придумали столичные заведения, чтобы работать даже в кризис",
          section: "Деньги и власть длинное",
          viewedDate: 1590598800,
          publishDate: 1590598640,
          image:
            "https://img.tyt.by/n/afisha/08/9/seafoodbar_by_john_dory_take_away.jpg"
        },

        {
          title:
            "Беларусь вошла в топ-10 стран по количеству зараженных COVID-19 на миллион населения",
          section: "Коронавирус",
          viewedDate: 1590598790,
          publishDate: 1590598550,
          image:
            "https://dh.img.tyt.by/720x720s/n/zamirovskiy/0e/7/05_dezinfekciya_transporta_koronavirus_20200401_zam_tutby_phsl.jpg"
        },
        {
          title:
            "Экономист о ВВП в 100 млрд долларов: «Не вижу предпосылок для такого оптимизма». Вот почему",
          section: "Доллар",
          viewedDate: 1590598750,
          publishDate: 1590598450,
          image:
            "https://dh.img.tyt.by/720x720s/n/ekonomika/0a/f/dengi_pensiya_zarplata_monety_valyuta_rubl.jpg"
        },
        {
          title:
            "Трамп пригрозил закрыть социальные сети из-за конфликта с Twitter. Об этом он сообщил в Twitter",
          section: "Популярное",
          viewedDate: 0,
          publishDate: 1590598350,
          image:
            "https://dh.img.tyt.by/720x720s/n/06/f/trump_tramp_27042020.jpg"
        },
        {
          title:
            "Турция и Черногория — возможно, Украина — пока нет. Куда белорусы смогут поехать на отдых этим летом",
          section: "Новость дня",
          viewedDate: 0,
          publishDate: 1590598320,
          image:
            "https://dh.img.tyt.by/552x368c/n/reuters/09/10/turciya_otdykh_reuters_rtr1tikc.jpg"
        },

        {
          title:
            "Вот что придумали столичные заведения, чтобы работать даже в кризис",
          section: "Деньги и власть длинное",
          viewedDate: 0,
          publishDate: 1590598300,
          image:
            "https://img.tyt.by/n/afisha/08/9/seafoodbar_by_john_dory_take_away.jpg"
        },

        {
          title:
            "Беларусь вошла в топ-10 стран по количеству зараженных COVID-19 на миллион населения",
          section: "Коронавирус",
          viewedDate: 0,
          publishDate: 1590598250,
          image:
            "https://dh.img.tyt.by/720x720s/n/zamirovskiy/0e/7/05_dezinfekciya_transporta_koronavirus_20200401_zam_tutby_phsl.jpg"
        },
        {
          title:
            "Экономист о ВВП в 100 млрд долларов: «Не вижу предпосылок для такого оптимизма». Вот почему",
          section: "Доллар",
          viewedDate: 0,
          publishDate: 1590598220,
          image:
            "https://dh.img.tyt.by/720x720s/n/ekonomika/0a/f/dengi_pensiya_zarplata_monety_valyuta_rubl.jpg"
        },
        {
          title:
            "Трамп пригрозил закрыть социальные сети из-за конфликта с Twitter. Об этом он сообщил в Twitter",
          section: "Популярное",
          viewedDate: 0,
          publishDate: 1590598180,
          image:
            "https://dh.img.tyt.by/720x720s/n/06/f/trump_tramp_27042020.jpg"
        }
      ]
    };
  },
  methods: {
    getTimestamp: datetime => {
      // datetime = '28.05.2020'
      const dt = datetime.split(".");

      console.log(dt);
      //return new Date().parse(`${month[m]} ${d}, ${y}`).getTime();
      return new Date(`${datetime} 00:00:00`).getTime() / 1000;
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
  margin: 0;
  li {
    display: inline-block;
    cursor: pointer;

    img {
      border: 2px solid #ff5555;
      box-sizing: border-box;
    }
    &.viewed {
      img {
        border-color: transparent;
      }
    }
  }
}
</style>
