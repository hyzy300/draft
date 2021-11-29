<template>
  <div id="app">
    <div class="home">
      <div class="head-line">
        <div class="head-item"><slot class="head-item"><img alt="cth" src="@\assets\img\cth.png"></slot></div>
        <div class="head-item"><slot class="head-item"><div class="head-item2"></div></slot></div>
      </div>
      <div class="header">
        <div class="menu-item"><slot class="menu-item"><li>首页</li></slot></div>
        <div class="menu-item"><slot class="menu-item"><li>coc是什么</li></slot></div>
        <div class="menu-item"><slot class="menu-item"><li>剧本</li></slot></div>
        <div class="menu-item"><slot class="menu-item"><li>车卡</li></slot></div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name
};
</script>

<style>
  .head-line {
    display: flex;
    height: 80px;
  }
  .head-item {
    flex: 1;
    height: 80px;
    color: rgb(129, 175, 201);
    background-color: #1e81af;
    float: left;
  }
  .head-item2 {
     flex: 1;
    height: 80px;
    color: rgb(227, 231, 233);
    background-color: #1e81af;
    font-size: 40px;

  }
  .header {
    display: flex;
    line-height: 50px;
    top: 50px;
  }
  .menu-item {
    flex: 1;
    text-align: center;
    
    height: 49px;
    color: rgb(129, 175, 201);
    background-color: #1b0657;
    top: 50px;
  }

</style>