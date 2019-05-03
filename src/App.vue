<template>
  <div id="app">
     <!--allmap->地图容器，无内容-->
        <div id="allmap"></div>
    <!-- <img src="./assets/logo.png"> -->
    <!-- <router-view/> -->
     <keep-alive>
            <router-view :shouldChangeCity="shouldChangeCity" :cityName="cityName"></router-view>
        </keep-alive>
    <tabbar>
      <tabbar-item selected link="/">
        <img slot="icon" src="./assets/images/home.png" >
        <span slot="label">订场</span>
      </tabbar-item>
      <tabbar-item link="/order">
        <img slot="icon" src="./assets/images/book.png">
        <span slot="label">订单</span>
      </tabbar-item>
      <tabbar-item  show-dot  link="/component/demo">
        <img slot="icon" src="./assets/images/my.png">
        <span slot="label">我的</span>
      </tabbar-item>
    </tabbar>
</div>

</template>

<script>
import { Tabbar, TabbarItem } from 'vux'
export default {
  name: 'App',
  components: {
    Tabbar,
    TabbarItem,
  
  },
  data(){
    return{
        cityName: '定位中',
        shouldChangeCity: true,
        
    }
  }
}
</script>

<style>
a {color: #000;text-decoration: none;}
.weui-tabbar {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    position: fixed !important;
    z-index: 500;
    bottom: 0;
    width: 100%;
    background-color: #F7F7FA;
}
.weui-tabbar__item.weui-bar__item_on .weui-tabbar__icon, .weui-tabbar__item.weui-bar__item_on .weui-tabbar__icon > i, .weui-tabbar__item.weui-bar__item_on .weui-tabbar__label {
    color: #00bcd4 !important;
}
.weui-tabbar__label {
    text-align: center;
    color: #999999;
    font-size: 12px !important;
    line-height: 0 !important;
}

</style>
