<template>
  <div id="app">
      <v-header :seller="seller"></v-header>
      <div class="tab border-1px">
          <div class="tab-item">
              <a v-link="{path: '/goods'}">商品</a>
          </div>
          <div class="tab-item">
              <a v-link="{path: '/ratings'}">评论</a>
          </div>
          <div class="tab-item">
              <a v-link="{path: '/seller'}">商家</a>
          </div>
      </div>
      <router-view :seller="seller"></router-view>
  </div>
</template>

<script>
import header from './components/header/header.vue';

export default {
  components: {
    'v-header': header
  },
  data () {
    return {
        seller: {}
    };
  },
  created () {
      this.$http.get('/api/seller').then((res) => {
          if (res.data.status === 1) {
              this.seller = res.data.data;
          };
      });
  }
};
</script>

<style lang="stylus" rel="stylesheet/stylus">
    @import './common/stylus/mixin.styl'
    #app
        .tab
            display: flex
            width: 100%
            height: 40px
            line-hight: 40px
            //border-bottom: 1px solid rgba(1,17,27,0.1)
            border-1px(rgba(1,17,27,0.1))
            .tab-item
                flex: 1
                text-align: center
                & > a
                    display: block
                    font-size: 14px
                    color: rgb(77,85,93)
                    &.active
                        color: rgb(240,20,20)
</style>
