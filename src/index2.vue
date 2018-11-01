<template>
  <wxc-tab-bar :tab-titles="tabTitles" :tab-styles="tabStyles" title-type="icon" @wxcTabBarCurrentTabSelected="wxcTabBarCurrentTabSelected">
    <!-- 第一个页面内容-->
    <div class="item-container" :style="contentStyle">
      <wxc-minibar title="首页" background-color="#FFFFFF" text-color="#3D3D3D" leftButton="">
      </wxc-minibar>

      <text>首页</text>
    </div>

    <!-- 第二个页面内容-->
    <div class="item-container" :style="contentStyle">
      <wxc-minibar title="电影" background-color="#FFFFFF" text-color="#3D3D3D" leftButton="">
      </wxc-minibar>
      <!-- <text>电影</text> -->
      <MovieList></MovieList>
    </div>

    <!-- 第三个页面内容-->
    <div class="item-container" :style="contentStyle">
      <wxc-minibar title="电影" background-color="#FFFFFF" text-color="#3D3D3D" leftButton="">
      </wxc-minibar>
      <text>我的</text>
    </div>
  </wxc-tab-bar>
</template>

<style scoped>
.item-container {
  width: 750px;
  background-color: #f2f3f4;
}
</style>

<script>
import { WxcTabBar, Utils, WxcMinibar } from 'weex-ui'
import MovieList from './components/movie/MovieList'
export default {
  name: 'App',
  components: { WxcTabBar, WxcMinibar, MovieList },
  data() {
    return {
      tabTitles: [
        {
          title: '首页',
          icon:
            'https://gw.alicdn.com/tfs/TB1MWXdSpXXXXcmXXXXXXXXXXXX-72-72.png',
          activeIcon:
            'https://gw.alicdn.com/tfs/TB1kCk2SXXXXXXFXFXXXXXXXXXX-72-72.png'
        },
        {
          title: '电影',
          icon:
            'https://gw.alicdn.com/tfs/TB1Do3tSXXXXXXMaFXXXXXXXXXX-72-72.png',
          activeIcon:
            'https://gw.alicdn.com/tfs/TB1LiNhSpXXXXaWXXXXXXXXXXXX-72-72.png'
        },
        {
          title: '我的',
          icon:
            'https://gw.alicdn.com/tfs/TB1ARoKSXXXXXc9XVXXXXXXXXXX-72-72.png',
          activeIcon:
            'https://gw.alicdn.com/tfs/TB1ARoKSXXXXXc9XVXXXXXXXXXX-72-72.png'
        }
      ],
      tabStyles: {
        bgColor: '#FFFFFF',
        titleColor: '#666666',
        activeTitleColor: '#3D3D3D',
        activeBgColor: '#FFFFFF',
        isActiveTitleBold: true,
        iconWidth: 70,
        iconHeight: 70,
        width: 160,
        height: 120,
        fontSize: 24,
        textPaddingLeft: 10,
        textPaddingRight: 10
      }
    }
  },
  created() {
    const tabPageHeight = Utils.env.getPageHeight()

    const { tabStyles } = this
    this.contentStyle = { height: tabPageHeight - tabStyles.height + 'px' }
  },
  methods: {
    wxcTabBarCurrentTabSelected(e) {
      const index = e.page
      // console.log(index);
    }
  }
}
</script>
