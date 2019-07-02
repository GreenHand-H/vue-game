import ad-1 from '../../assets/ad-1.jpeg';
<template>
  <!-- 攻略中心			 -->
  <div class="strategy">
    <h3 class="spr-1 start-tit text-hide">攻略中心</h3>
    <ul class="strategy-list">
      <li v-for="i in 4 " :key="i" class="strategy-item " :class="{active:stratData.index==i}" >
        <p class="spr-2 list-menu text-hide" @click="changeImg(i)">{{stratData.conData.title}}</p>
        <div class="strategy-info">
          <div class="strategy-swiper">
            <ul :class="{transition:stratData.conData.condex<3}" :style="{marginLeft:-stratData.condex*6.3+'rem',}">
              <li v-for="(el,j) in stratData.conData[0].urls" :key="j">
                <img :src="el.url" alt />
                <span>
                  <b>{{el.text}}</b>
                </span>
              </li>
            </ul>
            <div class="swiperStrategy-pagination">
              <span v-for="s in 3"  :key="s" class="swiper-pagination-bullet " :class="{'swiper-pagination-bullet-active':s-1==stratData.condex}" @click=" swiMoveTo(s-1)"></span>
             
            </div>
          </div>
          <ul class="strategy-info-list">
            <li>
              <a href="javascript:;">
                <span>[官方指引]</span>玩法爆料|御灵团战规则介绍
              </a>
              <span class="time">04-25</span>
            </li>
            <li>
              <a href="javascript:;">
                <span>[官方指引]</span>玩法爆料|御灵团战规则介绍
              </a>
              <span class="time">04-25</span>
            </li>
            <li>
              <a href="javascript:;">
                <span>[官方指引]</span>玩法爆料|御灵团战规则介绍
              </a>
              <span class="time">04-25</span>
            </li>
          </ul>
          <a href="javascript:;" class="strategy-more-btn">
            查看更多
            <span class="spr-1"></span>
          </a>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      stratData: {
        index: 1,
        conData:[ {
          title: "官方指引",
          urls: [
            { url: require("../../assets/ad-1.jpeg"),
            text:"【捉妖图鉴】进阶玩法：新世界BOSS朱雀技能及培养前景分析",
            time:'07-01' },
            { url: require("../../assets/ad-2.jpeg"),
            text:"【捉妖图鉴】进阶玩法：新世界BOSS朱雀技能及培养前景分析",
            time:'07-01'  },
            { url: require("../../assets/ad-3.jpeg"),
            text:"【捉妖图鉴】进阶玩法：新世界BOSS朱雀技能及培养前景分析",
            time:'07-01'  }
          ],
        }],
        condex:0,
        timer:'',
      }
    };
  },
//   数据
    methods: {
        changeImg(to){
            this.stratData.index=to;
        },
        swiMoveTo(to){
            var i=this.stratData.condex;
            if(to==undefined){
                to=i+1;
            }
            i=to;
            
            if(i==3){
                i=0;
            }
            this.stratData.condex=i;
        }
    },
    mounted(){
        this.timer=setInterval(() => {
                this.swiMoveTo();
        }, 3000);
    }
};
</script>
<style scoped>
.strategy {
  height: 16rem;
}
.strategy .start-tit {
  width: 7.02rem;
  height: 1.22rem;
  background-position: -0.1rem -2.7rem;
  margin: 0.4rem auto 0.5rem;
}

.strategy-list {
  width: 6.9rem;
  margin: auto;
}
.strategy-list li.strategy-item {
  height: 1.3rem;
  transition: height 0.5s linear;
  overflow: hidden;
  margin-bottom: 0.12rem;
}
.strategy-list li.strategy-item.active {
  height: 8.2rem;
}
.strategy-list li.strategy-item p.list-menu {
  text-indent: -9999rem;
  width: 6.9rem;
  height: 1.3rem;
}
.strategy-list li.strategy-item:nth-child(1) p.list-menu {
  background-position: -0.1rem -0.6rem;
}
.strategy-list li.strategy-item:nth-child(1).active p.list-menu {
  background-position: -0.1rem -2rem;
}
.strategy-list li.strategy-item:nth-child(2) p.list-menu {
  background-position: -0.1rem -3.4rem;
}
.strategy-list li.strategy-item:nth-child(2).active p.list-menu {
  background-position: -0.1rem -4.8rem;
}
.strategy-list li.strategy-item:nth-child(3) p.list-menu {
  background-position: -0.1rem -6.2rem;
}
.strategy-list li.strategy-item:nth-child(3).active p.list-menu {
  background-position: -0.1rem -7.6rem;
}
.strategy-list li.strategy-item:nth-child(4) p.list-menu {
  background-position: -0.1rem -9rem;
}
.strategy-list li.strategy-item:nth-child(4).active p.list-menu {
  background-position: -0.1rem -10.4rem;
}
.strategy-info {
  width: 100%;
  height: 6.9rem;
  background: url("../../assets/strategy-bg.jpg") no-repeat 0 0/100% 100%;
  border-radius: 0.3rem;
  overflow: hidden;
  padding: 0.3rem;
  box-sizing: border-box;
}
.strategy-swiper {
  width: 100%;
      height: 3.3rem;
  overflow: hidden;
  position: relative;
}
.strategy-swiper ul {
    width: 18.9rem;
    height: 3.3rem;
    overflow: hidden;
}
.strategy-swiper ul.transition{
    transition: all .5s linear;
}
.strategy-swiper ul li {
  float: left;
  height: 3.3rem;
  width: 6.3rem;
  position: relative;
}
.strategy-swiper ul li img {
  width: 100%;
  height: 100%;
}
.strategy-swiper ul li span {
  display: block;
  height: 0.55rem;
  background: rgba(0, 0, 0, 0.4);
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
}
.strategy-swiper ul li span b {
  display: block;
  width: 4.2rem;
  line-height: 0.55rem;
  margin-left: 0.3rem;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  color: #fff;
  font-weight: 300;
}
.swiperStrategy-pagination {
  display: flex;
  height: 0.55rem;
  position: absolute;
  bottom: 0;
  right: 0.1rem;
  align-items: center;
  z-index: 1;
}
.swiperStrategy-pagination .swiper-pagination-bullet {
  width: 0.5rem;
  height: 0.5rem;
  background: url("../../assets/icon1.png") no-repeat -5.95rem -0.35rem/15rem
    9.3rem;
  opacity: 1;
}
.swiperStrategy-pagination .swiper-pagination-bullet-active {
  width: 0.5rem;
  height: 0.5rem;
  background: url("../../assets/icon1.png") no-repeat -5.25rem -0.35rem/15rem
    9.3rem;
}
.strategy-info-list {
  margin-top: 0.1rem;
  color: #fff;
}
.strategy-info-list li {
  line-height: 0.6rem;
  position: relative;
  display: flex;
  border-bottom: 1px dashed #a6a6a6;
}
.strategy-info-list li:before {
  display: block;
  content: "";
  width: 0.17rem;
  height: 0.17rem;
  background: url("../../assets/icon1.png") -12.2rem -3rem/15rem 9.3rem;
  position: absolute;
  left: 0.1rem;
  top: 50%;
  margin-top: -0.085rem;
}
.strategy-info-list li a {
  padding-left: 0.4rem;
  width: 4.3rem;
  margin-right: 0.8rem;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}
.strategy-more-btn {
  margin-top: 0.2rem;
  display: flex;
  width: 3.4rem;
  height: 0.72rem;
  color: #5caafb;
  border: 2px solid #5caafb;
  border-radius: 0.2rem;
  align-items: center;
  justify-content: center;
  margin: 0.2rem auto 0;
  font-size: 0.34rem;
}
.strategy-more-btn span {
  display: block;
  width: 0.46rem;
  height: 0.33rem;
  background-position: -4.9rem -6.9rem;
  margin-left: 0.18rem;
}
</style>
