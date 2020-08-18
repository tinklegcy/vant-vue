<template>
  <div id="app">
    <!-- <router-view v- ="!$route.meta.keepAlive"></router-view>
    <keep-alive>
      <router-view v-if="$route.meta.keepAlive"></router-view>
    </keep-alive> -->
 <!-- <van-tabbar v-model="active">
  <van-tabbar-item icon="home-o">标签</van-tabbar-item>
  <van-tabbar-item icon="search">标签</van-tabbar-item>
  <van-tabbar-item icon="friends-o">标签</van-tabbar-item>
  <van-tabbar-item icon="setting-o">标签</van-tabbar-item>
</van-tabbar> -->
  <router-view />

<van-tabbar route class="active_tab">
  <van-tabbar-item replace to="/" icon="home-o" class="active_tab-font">
    首页
  </van-tabbar-item>
  <van-tabbar-item replace to="/about" icon="search">
    客户管理
  </van-tabbar-item>
   <van-tabbar-item replace to="/" icon="home-o">
    统计
  </van-tabbar-item>
  <van-tabbar-item replace to="/about" icon="search">
    我的
  </van-tabbar-item>
</van-tabbar>
  </div>
</template>

<script>
import Vue from 'vue';
import { Tabbar, TabbarItem } from 'vant';

Vue.use(Tabbar);
Vue.use(TabbarItem);
export default {
  data() {
    return {
      active: 0,
    };
  },
  methods: {
    push() {
      this.$router.push({ path: "/about" });
    },
  },
};
</script>

<style lang="less">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  width: 100% ;
  height: 100%;
  // width: 828px;
  font-size: 16px; /*px*/
  background: #F5F5F5;
  box-sizing: border-box;
  text-align: center;
}
.active_tab {
  height:165px;

}
.van-tabbar-item__text {
  font-size:22px;
}
.van-tabbar-item__icon {
    font-size:40px;
}
</style>
