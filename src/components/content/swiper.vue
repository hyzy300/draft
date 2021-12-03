<template>
  <div id="swiper">
    <div class="swipe" @touchstart="touchStart" @touchmove="touchMove" @touchend="touchEnd">
      <slot></slot>
    </div>
    <slot name="indicator"></slot>
    <div name="indicator">
      <slot name="indicator" v-if="showIndicator && slideCount>1">
        <div v-for="(item,liem) in slideCount" class="indi-item" :class="{active: index === currentIndex-1}" :key="index"></div>
      </slot>
    </div>
  </div>
</template>

<script>

export default defineComponent({
  name: 'Swiper',
  props: {
    interval: {
      type: Number,
      default: 3000,
    },
    delay: {
      type: Number,
      default: 300,
    },
    moveRadio: {
      type: Number,
      default: 0.25,
    },
    showIndicator: {
      type: Boolean,
      default: true,
    },
  },
  data: function(){
    return {
      slideCount: 0, //元素个数
      totalWidth: 0, //swiper宽度
      swiperStyle: {}, //swiper样式
      currentIndex: 1, //当前的index
      scrolling: false, //是否正在滚动
    }
  },
  mounted: function(){
    //操作DOM
    setTimeout(() => {
      this.handleDom();

      //开始计时
      this.startTimer();
    },100)
  },
  methods: {
    //定时器操作
    startTimer: function(){
      this.playTimer = window.setInterval(() => {
        this.currentIndex++;
        this.scrollContent(-this.currentIndex * this.totalWidth);
      },this.interval)
    },
    stopTimer: function(){
      window.clearInterval(this.playTimer);
    },

    //滚动到正确位置
    scrollContent: function(){
      //设置正在滚动
      this.scrolling = true;

      //开始滚动动画
      this.swiperStyle.transition = 'transform ' + this.delay + 'ms';
      this.setTransform(currentPosition);

      //判断滚动的位置
      this.checkPosition();

      //滚动完成
      this.scrolling = false;
    },

    //校验正确位置
    checkPosition: function(){
      window.setTimeout(() => {
        this.swiperStyle.transition = '0ms';
        if(this.currentIndex >= this.slideCount + 1){
          this.currentIndex = 1;
          this.setTransform(-this.currentIndex * this.totalWidth);
        } else if (this.currentIndex <= 0) {
          this.currentIndex = this.slideCount;
          this.setTransform(-this.currentIndex * this.totalWidth);
        }
      },this.delay)
    },

    //设置滚动位置
    setTransform: function(position){
      this.swiperStyle.transform = `translated3d(${position}px, 0, 0)` ;
      this.swiperStyle[`-webkit-transform`] = `translated3d(${position}px, 0, 0)` ;
      this.swiperStyle[`-ms-transform`] = `translated3d(${position}px, 0, 0)` ;
    },

    //操作DOM，在DOM后面添加slide
    handleDom: function(){
      //获取要操作的元素
      // let
    }
  },
  setup() {
    
  },
})
</script>
