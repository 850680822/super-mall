<template>
  <div class="news" v-if="Object.keys(this.newsData).length !== 0">
    <news-item
      v-for="(item, index) of this.newsData.list"
      :key="index"
      :goods="item"
      class="news-item"
    ></news-item>
  </div>
</template>
<script>
import newsItem from './NewsItem.vue'
export default {
  name: 'News',
  props: {
    newsData: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {}
  },
  components: {
    newsItem
  }
}
</script>
<style scope>
.news {
  display: flex;
  width: 100%;

  flex-wrap: wrap;
  text-align: center;
  justify-content: space-around; /* 产生了一个两边跨列并且两边都有缝隙的一个形态*/
}
.news-item {
  flex: 0 0 48%;
  width: 50%;

  /* padding: 10px; */
}
</style>
