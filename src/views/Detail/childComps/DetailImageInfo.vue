<template>
  <div class="img-info" v-if="Object.keys(this.detList).length !== 0">
    <!-- 图片参数详情模块开发 -->
    <div class="img-info-warp">
      <div>
        <span>{{ detList.title }}</span>
      </div>
      <div class="imglist" v-for="(item, index) of detList.list" :key="index">
        <van-image :src="item" @load="onload">
          <template v-slot:loading>
            <van-loading type="spinner" size="20" />
          </template>
          <template v-slot:error>加载失败</template>
        </van-image>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailImageInfo',
  props: {
    detList: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {}
  },
  methods: {
    onload() {
      this.$bus.$emit('imgInfoOnload')
    }
  }
}
</script>
<style lang="less" scoped>
.img-info {
  font-size: 0.8rem;
  padding: 0 0.5rem;
  margin: 0.5rem 0;

  .img-info-warp {
    border-bottom: 0.4rem solid #eee;
    .imglist {
      width: 100%;
      van-image {
        width: 100%;
      }
    }
  }
}
</style>
