<template>
  <div>
    <div class="banner"
         @click="handleBannerClick">
      <img :src="bannerImg"
           class="banner-img">
      <div class="banner-info">
        <div class="banner-title">
          {{this.sightName}}
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          {{this.bannerImgs.length}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary :imgs="bannerImgs"
                      v-show="showGallary"
                      @close="handleGallaryClose">
      </common-gallary>
    </fade-animation>
  </div>
</template>
<script>
import CommonGallary from '../../common/Gallary'
import FadeAnimation from '../../common/Fade'
export default {
  data () {
    return {
      imgs: [],
      showGallary: false
    }
  },
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  created () { },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary,
    FadeAnimation
  }
}
</script>
<style lang="less" scoped>
.banner {
  position: relative;
  overflow: hidden;
  padding-bottom: 55%;
  height: 0;
  .banner-img {
    width: 100%;
  }
  .banner-info {
    position: absolute;
    background-image: linear-gradient(
      to bottom,
      rgba(0, 0, 0, 0),
      rgba(0, 0, 0, 0.8)
    );
    left: 0;
    right: 0;
    bottom: 0;
    line-height: 0.6rem;
    display: flex;
    color: #fff;
    .banner-title {
      flex: 1;
      font-size: 0.32rem;
      padding: 0.2rem;
    }
    .banner-number {
      margin-top: 0.14rem;
      padding: 0 0.4rem;
      height: 0.4rem;
      line-height: 0.32rem;
      border-radius: 0.2rem;
      font-size: 0.24rem;
      background: rgba(0, 0, 0, 0.8);
      .banner-icon {
        font-size: 0.24rem;
      }
    }
  }
}
</style>
