<template>
  <div id="app" style="height:100%;width:100%">
     <!-- <router-view></router-view> -->
   <drawer width="200px">
      <div slot="drawer">
        <p>测试侧边栏</p>
      </div>
      <view-box ref="viewBox" body-padding-top="46px" body-padding-bottom="55px">
        <router-view></router-view>
        <tabbar class="vux-demo-tabbar" icon-class="vux-center" slot="bottom">
          <tabbar-item :link="{path:'/'}">  
            <span class="demo-icon-22 vux-demo-tabbar-icon-home" slot="icon" style="position:relative;top: -2px;">&#xe637;</span>
            <span slot="label">Home</span>
          </tabbar-item>
          <tabbar-item :link="{path:'/demo'}" badge="9">
            <span class="demo-icon-22" slot="icon">&#xe633;</span>
            <span slot="label"><span>Demos</span></span>
          </tabbar-item>
        </tabbar>
      </view-box>
      

    </drawer> 
    
  </div>
</template>

<script>
import {Drawer, Tabbar, TabbarItem,ViewBox,ButtonTab, ButtonTabItem} from 'vux';
export default {
  name: 'app',
  data: function(){
    return {
      isDemo: true,
      componentName: false,

    }
  },
  components: {
    Drawer,
    Tabbar,
    TabbarItem,
    ViewBox,
    ButtonTab, 
    ButtonTabItem,
  }
}
</script>

<style lang="less">
@import '~vux/src/styles/reset.less';
@import '~vux/src/styles/1px.less';
@import '~vux/src/styles/tap.less';
html, body {
    height: 100%;
    width: 100%;
    overflow-x: hidden;
}
body {
  background-color: #fbf9fe;
}

@font-face {  //指定字体，并指定哪里可以找到它的URL
  font-family: 'vux-demo';  /* project id 70323 */
  //src: url('http://at.alicdn.com/t/font_70323_wlronpvr565yiudi.eot');
  src:
  url('./assets/font.ttf') format('truetype'),
  //url('http://at.alicdn.com/t/font_70323_wlronpvr565yiudi.svg#iconfont') format('svg');
}

.demo-icon-22 {
  font-family: 'vux-demo';
  font-size: 22px;
  color: #888;
}

.demo-icon-22:before {
  content: attr(icon);
}


</style>
