<template>
  <div id="app">
    <div class="home">
      <div class="background">
        <img src="@/assets/img/background.jpg" alt="back" class="background"/>
      </div>
      <div class="head-line">
        <div class="head-item"><slot class="head-item"><img alt="cth" src="@/assets/img/cth.png"></slot></div>
        <div class="head-item"><slot class="head-item"><div class="head-item"></div></slot></div>
      </div>
      <div class="header">
        <div class="head-item2"><slot class="head-item2"><div @click="mainPageClick">首页</div></slot></div>
        <div class="head-item2"><slot class="head-item2"><a>coc是什么</a></slot></div>
        <div class="head-item2"><slot class="head-item2"><a>剧本</a></slot></div>
        <div class="head-item2">
          <slot class="head-item2" @click="characterClick">
            <!-- <router-link to="/about"> -->
            <div @click="characterClick">车卡</div>
            <!-- </router-link> -->
            <!-- <router-view/> -->
            </slot></div>
      </div>
      <div class="a-wrap">
        
        <div class="a-column2">
          <!-- <slot class="mainpic-item">
            <img alt="Squidward" src="@\assets\img\Squidward.jpg" class="mainpic-item">
            </slot> -->
            <slot class="mainpic-item">
              <swipe></swipe>
            </slot>
        </div>
        <div class="a-column3">
          <slot class="mainpic-item">
            <br /><p>When the stars return, chaos will rise from the earth and the great will awaken.</p>
            <br /><p>当群星归位之时,混沌将从地底升起,伟大的最初将会苏醒。</p>
          </slot>
          
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import { defineComponent, ref } from 'vue'
import Character from './character.vue'
import Swipe from '../components/content/swipe.vue'
import {
  Location,
  Document,
  Menu as IconMenu,
  Setting,
} from '@element-plus/icons'

export default {
  props: {
    link: String
  },
  data() {

  },
  methods: {
    characterClick() {
      // console.log("111");
      this.$router.push('/About')
    },
    mainPageClick() {
      this.$router.push('/Home')
    }
  },
  components: {
    Location,
    Document,
    Setting,
    IconMenu,
    Character,
    Swipe
  },
  setup() {
    const isCollapse = ref(true)
    const handleOpen = (key, keyPath) => {
      console.log(key, keyPath)
    }
    const handleClose = (key, keyPath) => {
      console.log(key, keyPath)
    }
    return {
      isCollapse,
      handleOpen,
      handleClose,
    }
  },
};
</script>

<style>
  /* .home {
    margin:0;
    padding:0;
  } */
  .head-line {
    display: flex;
    height: 80px;
  }
  .header {
    display: flex;
    line-height: 50px;
    top: 50px;
  }
  .mainpic {
    max-width: 600px;
    max-height: 480px;
    margin-left: 60px;
  }
  .mainpic-item {
    max-width: 100%;
    max-height: 100%;
  }
  .head-item {
    flex: 1;
    height: 80px;
    color: rgb(129, 175, 201);
    background-color: #0b3447;
    float: left;
  }
  .head-item2 {
     flex: 1;
    height: 60px;
    color: rgb(227, 231, 233);
    background-color: #1e81af;
    font-size: 1.2rem;
    text-align: center;
  }
  .menu-item {
    flex: 1;
    height: 80px;
    /* color: rgb(129, 175, 201); */
    /* background-color: #1e81af; */
    float: left;
  }
  
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 20%;
    min-height: 400px;
    float: left;
    display: inline;
  }
  .a-column2 {
    margin-left: 5%;
    width: 50%;
    float: left;
    display: flex;
  }
  .a-column3 {
    margin-left: 1%;
    width: 30%;
    max-height: 400px;
    float: left;
    font-style: italic;
    font-size: 1.2rem;
    color: rgb(247, 243, 8);
    display: table-column;
    overflow: hidden;
    
  }
  .background{
    width: 100%;  
    height: 100%;  /**宽高100%是为了图片铺满屏幕 */
    z-index: -1;
    position: absolute;
}



</style>