<template>
<div class="head">
    <section class="header"> 
        <div class="header-logo">
            <h1>
                <a href="javascript:;"></a>
            </h1>
            <div class="header-desc">
            <h2>一起来捉妖</h2>
            <p>腾讯首款AR探索手游</p>
        </div>
        </div>
        
        <div class="header-btns">
            <a href="javascript:;" class="header-btn db">立即下载</a>
            <ul :class="{open}" @click="open=!open">
                <li>——</li>
                <li>——</li>
                <li>——</li>
            </ul>
        </div>
    </section>
    <nav class="nav " :class="{open}">
        <ul class="nav-list " >
        <li v-for="(elem,i) in navData" :key="i" class="active">
              <!-- <router-link to="http://www.baidu.cn"  target="_blank">  {{elem}}</router-link> -->
              <a href="javascript:;">{{elem}}</a>
        </li>
        </ul>
    </nav>
   
    </div>
</template>
<script>
export default {
    data(){
        return {
            open:false,
            navData:["官网首页","新闻中心","精彩视频","攻略中心","妖精图鉴","活动中心"],
        }
    },
     

}
</script>
<style scoped>
.header{
    width: 100%;
    height: 1.2rem;
    display: flex;
    background: #4a77ae;
    justify-content: space-between;
    align-items: center;
    padding: 0 .3rem;
    box-sizing: border-box;
    color: #fff;
    z-index: 11;
    position: fixed;
    top:0;
    left: 0;
}
.header-logo{
    display: flex;
    align-items: center;
}
.header-logo h1{
    width: 1.44rem;
    height: .96rem;
}
.header h1 a{
    display: block;
    width: 100%;
    height: 100%;
    background: url("../assets/logo.png") no-repeat;
    background-size:100% 100%;
    text-indent:-999rem;
}
.header-desc{
    margin-left: .2rem;
}
.header-desc h2{
    font-size: .36rem;
    font-weight: 500;
    line-height: 1;
}
.header-desc p{
    line-height: 1;
    font-size: .24rem;
    margin-top: .1rem;
    color:#b0d5ff;
}
.header-btns{
    display: flex;
    align-items: center;
}
.header-btn{
    width: 1.8rem;
    height: .65rem;
    line-height: .65rem;
    text-align: center;
    border:1px solid #b7c9df;
    border-radius:.6rem;
    font-size: .3rem;
}
.header-btns ul{
    width:.53rem;
    height: .4rem;
    flex-direction: column;
    margin-left: .2rem;
}
.header-btns li{
    width: 100%;
    height: .04rem;
    background-color: #fff;
    box-sizing: border-box;
    transition: all .5s;
    text-indent: -999rem;
}
.header-btns li:not(:first-child){
    margin-top:.15rem;
}
.header-btns ul.open li:nth-child(1){
    transform-origin: left center;
    transform: rotate(45deg);
}
.header-btns ul.open li:nth-child(2){
    opacity: 0;
}
.header-btns ul.open li:nth-child(3){
    transform-origin: left center;
    transform: rotate(-45deg);
}
.nav.open{
    transform: translateY(0);
    opacity: 1;
}
.nav{
    display: flex;
    justify-content: center;
    position: fixed;
    left: 0;
    width: 100%;
    z-index: 10;
    background: rgba(0,0,0,.7);
    transform: translateY(-7.36rem);
    transition: transform .5s , opacity .5s;
    opacity: 0;
}
.nav-list{
    width  :100%;
}
.nav-list li{
    width:100%;
    box-sizing: border-box;
    padding:0 .3rem;
}
.nav-list a {
    display: block;
    width: 100%;
    height: 100%;
    position: relative;
    text-align: center;
    font-size: .3rem;
    color: #fff;
    box-sizing: border-box;
    line-height: .8rem;
}
.nav-list li:not(:last-child) a {
    border-bottom: 1px solid #939393;
}
</style>

