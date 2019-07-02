import icon1 from '../assets/icon1.png';
<template>
  <div class="home">
    <Head></Head>
    <!-- kv -->
    <div class="kv-wrap">
      <div class="kv-swiper swiper-container">
        <ul id="swiper-cont" ref="swiper1">
          <li class="swiper-item" ref="swiperWidth">
            <img src="../assets/kv1.jpg" alt />
          </li>
          <li class="swiper-item">
            <img src="../assets/kv2.jpg" alt />
          </li>
          <li class="swiper-item" ref="swiperWidth">
            <img src="../assets/kv1.jpg" alt />
          </li>
        </ul>
      </div>
    </div>
    <!-- 新闻中心  wrap-->
    <div class="news">
      <div class="mt-center">
        <ul class="adPic clear" ref="swiper2" :style="{marginLeft:-adData.adIndex*7.5+'rem',}" :class="{trasition:adData.adIndex<3}">
          <li v-for="(elem,i) in adData.urls" :key="i" >
            <!-- <img src="../assets/img/photo/ad-2.jpeg" > -->
            <img :src="elem.url" />
          </li>
          <!-- <a href="javascript:;" target="_blank">
              <img src="../assets/img/photo/ad-2.jpeg" alt>
          </a>-->
        </ul>
        <div class="adBtn">
          <a
            v-for="(elem,i) in adData.adText"
            :key="i"
            :class="{on:adData.adIndex==i}"
            @click.prevent="adMoveTo(i)"
          >{{elem}}</a>
          <!-- <a href="javascript:;">韶阳雪止，万物之生——五星神灵句芒现世</a> -->
        </div>
      </div>
      <!-- 新闻列表 -->
      <div class="mt-right">
        <ul class="tab-hd">
          <li
            v-for="(aElem,i) in mtData"
            :key="i"
            :class="{on:aElem.dis}"
            @mouseenter="addOn"
            :data-On="aElem.title"
          >
            <a href="javascript:;">{{aElem.title}}</a>
          </li>
          <!-- <li>
              <a href="javascript:;">新闻</a>
          </li>-->
        </ul>
        <div class="grid-tab-bd">
          <ul class="col-news" v-for="(eles,j) in mtData" :key="j" :class="{dis:eles.dis}">
            <li v-for="(elem,i) in eles.content" :key="i">
              <span class="time">{{elem.date}}</span>
              <a href="javascript:;">
                <span>{{elem.spanText}}</span>
                {{elem.contText}}
              </a>
            </li>
            <!-- <li><span class='time'>04-26</span><a href="javascript:;"><span>[新闻]</span>火爆捉妖，全城辣来袭</a></li> -->
          </ul>
        </div>
      </div>
      <a href="javascript:;" class="more-btn">查看更多</a>
    </div>
    <!-- 活动中心 -->
    <activityHome></activityHome>
    <strategyHome></strategyHome>
  </div>
</template>

<script>
// @ is an alias to /src
import Head from "@/components/head.vue";
import activityHome  from '@/components/Home/activityHome';
import strategyHome from '@/components/Home/strategyHome'
export default {
  name: "home",
  components: {
    Head,
    activityHome,
    strategyHome
  },
  data() {
    return {
      adData: {
        urls: [
          { url: require("../assets/ad-1.jpeg") },
          { url: require("../assets/ad-2.jpeg") },
          { url: require("../assets/ad-3.jpeg") }
        ],
        // 动态图片的加载需要require
        adIndex: 0,
        adTimer: "",
        adText: [
          "旬空一刻，亮采其华——全新亮采版本精彩上线",
          "韶阳雪止，万物之生——五星神灵句芒现世",
          "灿如星火问天机——一起来捉妖新版本上线"
        ]
      },
      mtData: [
        //   新闻资讯
        {
          title: "最新",
          dis: true,
          content: [
            {
              date: "04-26",
              spanText: "[新闻资讯]",
              contText: "【活动】明星擂台 限时开启"
            },
            {
              date: "04-26",
              spanText: "[新闻资讯]",
              contText: "【活动】明星擂台 限时开启"
            },
            {
              date: "04-26",
              spanText: "[新闻资讯]",
              contText: "【活动】明星擂台 限时开启"
            },
            {
              date: "04-26",
              spanText: "[新闻资讯]",
              contText: "【活动】明星擂台 限时开启"
            },
            {
              date: "04-26",
              spanText: "[新闻资讯]",
              contText: "【活动】明星擂台 限时开启"
            }
          ]
        },
        // 新闻
        {
          title: "新闻",
          dis: false,
          content: [
            {
              date: "04-26",
              spanText: "[新闻]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[新闻]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[新闻]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[新闻]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[新闻]",
              contText: "火爆捉妖，全城辣来袭"
            }
          ]
        },
        // 公告
        {
          title: "公告",
          dis: false,
          content: [
            {
              date: "04-26",
              spanText: "[公告]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[公告]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[公告]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[公告]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[公告]",
              contText: "火爆捉妖，全城辣来袭"
            }
          ]
        },
        // 活动
        {
          title: "活动",
          dis: false,
          content: [
            {
              date: "04-26",
              spanText: "[活动]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[活动]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[活动]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[活动]",
              contText: "火爆捉妖，全城辣来袭"
            },
            {
              date: "04-26",
              spanText: "[活动]",
              contText: "火爆捉妖，全城辣来袭"
            }
          ]
        }
        // 数据结束
      ]
    };
  },
  methods: {
    addOn(e) {
      var tit = e.target.dataset.on;
      for (var elem of this.mtData) {
        elem.dis = false;
        if (tit == elem.title) {
          elem.dis = true;
        }
      }
    },
    adMoveTo(to) {
      var todex = this.adData.adIndex;
      if (to == undefined) {
        to = todex + 1;
      }
      todex = to;
      if (todex == this.adData.urls.length) {
        todex = 0;
      }
      this.adData.adIndex = todex;
    }
  },
  mounted() {
    (() => {
      var i = 0;
      var swiperAll = this.$refs.swiper1;
      function moveTo(to) {
        if (to == undefined) {
          to = i + 1;
        }
        if (i == 0) {
          swiperAll.setAttribute("className", "transition");
        }
        i = to;
        if (i > 2) {
          i = 0;
          setTimeout(() => {
            swiperAll.setAttribute("className", "");
            swiperAll.style.left = "0rem";
          }, 500);
        } else {
          swiperAll.style.marginLeft = -i * 7.5 + "rem";
        }
      }
      setInterval(() => {
        moveTo();
      }, 3000);
    })();
    this.adData.adTimer = setInterval(() => {
      this.adMoveTo();
    }, 3000);
  }
};
</script>
<style scopes>
@import "../assets/css/reset.css";
.home {
  width: 100vm;
}
.kv-wrap {
  width: 100%;
  height: 10rem;
  position: relative;
  overflow: hidden;
}
.kv-swiper {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  overflow: hidden;
}
#swiper-cont {
  position: absolute;
  top: 0;
  left: 0;
}
#swiper-cont.transition {
  transition: all 0.5s linear;
}
#swiper-cont .swiper-item {
  width: 7.5rem;
  height: 10rem;
  float: left;
}
#swiper-cont .swiper-item img {
  width: 100%;
  height: 100%;
}
/* 轮播 */
.news{
  padding-top: 0.2rem;
}
.mt-center {
  width: 6.9rem;
  margin: auto;
  position: relative;
  overflow: hidden;
}
.adPic {
  width: 22.5rem;
  height: 3.62rem;
  overflow: hidden;
}
.adPic.transition {
  transition: all .5s linear;
}
.adPic li {
  width: 7.5rem;
  height: 3.62rem;
  float: left;
}
.adPic li img {
  width: 100%;
  height: 100%;
}
.adBtn {
  height: 0.55rem;
  position: absolute;
  bottom: 0;
  right: 0.1rem;
  align-items: center;
  z-index: 1;
}
.adBtn a {
  display: inline-block;
  text-indent: -500rem;
  overflow: hidden;
  width: 0.5rem;
  height: 0.5rem;
  background: url("../assets/icon1.png") no-repeat -5.95rem -0.35rem/15rem
    9.3rem;
  opacity: 1;
}
.adBtn a.on {
  width: 0.5rem;
  height: 0.5rem;
  background: url("../assets/icon1.png") no-repeat -5.25rem -0.35rem/15rem
    9.3rem;
}
/* 新闻列表 */
.mt-right {
  width: 100%;
  box-sizing: border-box;
  padding: 0 0.3rem;
}

.mt-right .tab-hd {
  justify-content: space-between;
  color: #a7cffb;
  height: 0.32rem;
  padding-top: 0.27rem;
  display: flex;
}

.mt-right .tab-hd > li {
  width: 1rem;
  height: 0.32rem;
  line-height: 0.32rem;
  position: relative;
  text-align: center;
  font-size: 0.32rem;
  display: flex;
  align-items: center;
}

.mt-right .tab-hd > li > a {
  padding-left: 5px;
  border-left: 4px solid transparent;
}
.mt-right .tab-hd > li.on {
  color: #5babfb;
  font-weight: 700;
}
.mt-right .tab-hd > li.on > a {
  border-left: 4px solid #78b5fb;
  color: #78b5fb;
}
.grid-tab-bd .col-news {
  display: none;
  margin-top: 0.25rem;
}
.grid-tab-bd .col-news.dis {
  display: block;
}
.col-news > li {
  width: 100%;
  height: 100%;
  position: relative;
  line-height: 0.85rem;
  color: #666666;
}

.col-news > li:before {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  right: 0;
  height: 1px;
  background: linear-gradient(
    to right,
    #b2c7e3,
    #b2c7e3 1px,
    transparent 1px,
    transparent
  );
  background-size: 8px 100%;
}

.col-news > li a {
  display: block;
  padding-right: 0.4rem;
  padding-left: 0.44rem;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.col-news > li a:before {
  content: "";
  display: block;
  width: 0.2rem;
  height: 0.21rem;
  position: absolute;
  top: 50%;
  left: 0.1rem;
  background: url("../assets/icon1.png") no-repeat -11.6rem -3rem/15rem 9.3rem;
  margin-top: -0.105rem;
}
.col-news > li .time {
  float: right;
}
.more-btn{
  display: flex;
    width: 3.4rem;
    height: .72rem;
    color: #5caafb;
    border: 2px solid #5caafb;
    border-radius: .2rem;
    align-items: center;
    justify-content: center;
    margin: .2rem auto 0;
    font-size: .34rem;
}
</style>

