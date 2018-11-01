<template>
  <div class="tabbar-wrp">
    <div @click="selectTab(index)" v-for="(item,index) in tabItems" :key="index" class="tabbar-item">
      <image class="tabbar-icon" :src="selectedIndex===index?item.selectedImage:item.image"></image>
      <text class="tabbar-text" :style="{color:item.titleColor}">{{item.title}}</text>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    tabItems: Object
  },
  data() {
    return {
      selectedIndex: 0 //默认选中的索引
    }
  },
  methods: {
    selectTab(index) {
      this.selectedIndex = index

      this.$emit('selectTab', index)
    }
  }
}
</script>

<style scoped>
.tabbar-wrp {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 750px;
  height: 88px;
  background-color: #fff;
  flex-direction: row;
  align-items: center;
  border-top-width: 2px;
  border-color: #e2e2e2;
}
.tabbar-item {
  flex: 1;
  text-align: center;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.tabbar-icon {
  width: 35px;
  height: 35px;
}
.tabbar-text {
  font-size: 18px;
  margin-top: 10px;
}
</style>