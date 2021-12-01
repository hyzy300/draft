<template>
  <div id="app">
    <div class="home">
      <div class="head-line">
        <div class="head-item"><slot class="head-item"><img alt="cth" src="@\assets\img\cth.png"></slot></div>
        <div class="head-item"><slot class="head-item"><div class="head-item"></div></slot></div>
      </div>
      <div class="header">
        <div class="head-item2"><slot class="head-item2"><a href="https://www.baidu.com/" class="head-item2">首页</a></slot></div>
        <div class="head-item2"><slot class="head-item2"><a>coc是什么</a></slot></div>
        <div class="head-item2"><slot class="head-item2"><a>剧本</a></slot></div>
        <div class="head-item2"><slot class="head-item2"><a>车卡</a></slot></div>
      </div>
    </div>
    <div>
      <div class="mainpic">
        <slot class="mainpic-item"><img alt="Squidward" src="@\assets\img\Squidward.jpg" class="mainpic-item"></slot>
      </div>
    </div>
    <!-- <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      :collapse="isCollapse"
      @open="handleOpen"
      @close="handleClose"
    >
      <el-submenu index="1" >
        <template #title>
          <el-icon><location /></el-icon>
          <span>Navigator One</span>
        </template>
        <el-menu-item-group>
          <template #title><span>Group One</span></template>
          <el-menu-item index="1-1">item one</el-menu-item>
          <el-menu-item index="1-2">item two</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="Group Two">
          <el-menu-item index="1-3">item three</el-menu-item>
        </el-menu-item-group>
        <el-submenu index="1-4">
          <template #title><span>item four</span></template>
          <el-menu-item index="1-4-1">item one</el-menu-item>
        </el-submenu>
      </el-submenu>
      <el-menu-item index="2">
        <el-icon><icon-menu /></el-icon>
        <template #title>Navigator Two</template>
      </el-menu-item>
      <el-menu-item index="3" disabled>
        <el-icon><document /></el-icon>
        <template #title>Navigator Three</template>
      </el-menu-item>
      <el-menu-item index="4">
        <el-icon><setting /></el-icon>
        <template #title>Navigator Four</template>
      </el-menu-item>
    </el-menu> -->
  </div>
</template>

<script>

import { defineComponent, ref } from 'vue'
import {
  Location,
  Document,
  Menu as IconMenu,
  Setting,
} from '@element-plus/icons'

export default {
    components: {
    Location,
    Document,
    Setting,
    IconMenu,
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
    width: 100%;
    height: 100%;
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
    font-size: 20px;
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
    width: 200px;
    min-height: 400px;
  }

</style>