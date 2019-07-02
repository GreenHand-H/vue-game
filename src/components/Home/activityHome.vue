import ad-1 from '../../assets/ad-1.jpeg';
<template>
     <!-- 活动中心-->
        <div class="part2">
            <div class="part2-inner clearfix">
                <h3 class="p2-tit spr-1 text-hide">活动中心</h3>
                <ul class="act-list">
                    <li class="act-0">
                        <img src="../../assets/ad-1.jpeg" alt="" />
                    </li>
                    <li>
                        <img src="../../assets/ad-2.jpeg" alt="" />
                    </li>
                    <li>
                        <img src="../../assets/ad-3.jpeg" alt="" />
                    </li>
                </ul>
                <a href="javascript:;" class="act-more-btn">查看更多
                    <span class="spr-1"></span>
                </a>
            </div>
        </div>
</template>
<style scoped>
/*活动中心*/

.part2 {
    height:10.8rem;
    overflow: hidden;
}

.part2-inner {
    width: 100%;
    margin: 0.1rem auto 0;
    position: relative;
}

.p2-tit {
    width: 6.52rem;
    height: 1.22rem;
    background-position: -.1rem -1.4rem !important;
    margin: .4rem auto .5rem;
    text-align: center;
}
.act-list{
    width: 6.9rem;
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}
.act-list li {
    width:3.38rem;
    height: 2.06rem; 
    border-radius:  .2rem;
    overflow: hidden; 
}

.act-list li.act-0 {
    width: 100%;
    height:4.2rem;
   margin-bottom: .2rem;
}

.act-list li img {
    width: 100%;
    height: 100%;
}
.act-more-btn {
    margin-top: .5rem;
    color: #a7751e;
    display: flex;
    width: 3.4rem;
    height: .72rem;
    border: 2px solid #a7751e;
    border-radius: .2rem;
    align-items: center;
    justify-content: center;
    margin: .2rem auto 0;
    font-size: .34rem;
}
.spr-1 {
    background: url('../../assets/icon1.png') no-repeat;
    background-size: 15rem 9.3rem;
}
.act-more-btn  span {
   background-position: -7.2rem -6.9rem;
   display: block;
   width: .46rem;
   height: .33rem;
   margin-left: .18rem;
}


</style>
