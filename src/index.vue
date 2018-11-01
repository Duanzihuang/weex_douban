<template>
  <div class="wrap">
    <div v-if="showIndex===0">
      <Home />
    </div>
    <div v-else-if="showIndex===1">
      <Movie />
    </div>
    <div v-else-if="showIndex===2">
      <Mine />
    </div>
    <tab-bar :tabItems="tabItems" @selectTab="selectTab"></tab-bar>
  </div>
</template>

<script>
import tabbar from './components/tabbar'
import Home from './components/home/Home'
import Movie from './components/movie/Movie'
import Mine from './components/mine/Mine'
export default {
  components: { tabBar: tabbar, Home, Movie, Mine },
  data() {
    return {
      showIndex: 0, //显示第几个页面
      tabItems: [
        {
          title: '首页',
          titleColor: '#000000',
          image: 'http://www.huangjiangjun.top/assets/tabBar/home_normal.png',
          selectedImage:
            'http://www.huangjiangjun.top/assets/tabBar/home_selected.png'
        },
        {
          title: '电影',
          titleColor: '#000000',
          image: 'http://www.huangjiangjun.top/assets/tabBar/movie_normal.png',
          selectedImage:
            'http://www.huangjiangjun.top/assets/tabBar/movie_selected.png'
        },
        {
          title: '我的',
          titleColor: '#000000',
          image: 'http://www.huangjiangjun.top/assets/tabBar/mine_normal.png',
          selectedImage:
            'http://www.huangjiangjun.top/assets/tabBar/mine_selected.png'
        }
      ]
    }
  },
  methods: {
    selectTab(index) {
      this.showIndex = index
    }
  }
}
</script>

<style scoped>
.wrap {
  background-color: #f0efe9;
}
.title {
  font-size: 24px;
  padding-top: 20px;
  padding-bottom: 10px;
  padding-left: 20px;
  padding-right: 20px;
  color: #3e434f;
}
</style>