<template>
    <view>
        <view class="index-header" :style="{backgroundImage: 'url(' + bg1 + ')' }">
            <view class="header-warn">完善信息，查看保养里程 ></view>
            <view class="header-warn" style="font-size: 10px; color: #a3a2a6;">晴  30℃  较适宜洗车</view>
        </view>
        <uni-swiper-dot :info="info" :current="current" :field="content" :mode="mode">
            <swiper autoplay="true" interval="3000" class="swiper-box" @change="change">
                <swiper-item v-for="(item ,index) in info" :key="index">
                    <view class="swiper-item">
                        <image class="image" :src="item.url" mode="aspectFill" />
                    </view>
                </swiper-item>
            </swiper>
        </uni-swiper-dot>
        <scroll-view scroll-x="true" class="scroll">
            <view class="store-server-item" v-for="(fw, i) in fws" :key="i">
                <image class="store-server-pic" :src="getImgUrl(fw.icon)"></image>
                <view class="store-server-txt">{{fw.mc}}</view>
            </view>
        </scroll-view>
        <view class="car-tips">
            <view class="car-tips-body">
                <view class="car-tips-body-l">
                    <view class="car-tips-txt1">你真的知道怎么保养爱车吗？</view>
                    <view class="car-tips-txt2">完善爱车信息，给爱车制定保养方案</view>
                    <view class="notice-bar">
                        <image class="notice-bar-icon" :src="tb1" />
                        <view class="notice-bar-msg">{{notice}}</view>
                    </view>
                </view>
                <view class="car-tips-body-r">
                    <view class="car-tips-btn">立即完善爱车</view>
                    <!--<view class="car-tips-btn">去保养</view>-->
                </view>
            </view>
        </view>
        <view class="index-title">
            <view class="index-title-l">品牌专区</view>
            <view class="index-title-r">更多  ></view>
            <image class="index-img" :src="pptp1"></image>
        </view>
    </view>
</template>

<script>
    import uniSwiperDot from "@/components/uni-swiper-dot/uni-swiper-dot.vue"
    export default {
        components: {
            uniSwiperDot
		},
        data() {
            return {
                content: '',
                info: [
                    {
						url: require('../../static/image/5.jpg'),
						content: '内容 A'
					},
					{
						url: require('../../static/image/6.jpg'),
						content: '内容 B'
					},
					{
						url: require('../../static/image/7.jpg'),
						content: '内容 C'
					},
                    {
                        url: require('../../static/image/8.jpg'),
                        content: '内容 D'
                    }
				],
                current: 0,
                mode: 'round',
                bg1: require('../../static/image/bg2.jpg'),
                fws: [],
                pptp1: require('../../static/image/1.jpg'),
                tb1: require('../../static/image/icon/icon-notice.png'),
                count: 0,
                notice: '',
                msgs: [
                    {msg: '定期养护爱车，我们为你保驾护航'},
                    {msg: '选择适合机油型号，保障发动机性能'},
                    {msg: '天气变热了，别让你胎压太高了'},
                    {msg: '爱车洗洗澡，车身光亮心情好'},
                    {msg: '机油也有保质期，别忘更换变过期'},
                    {msg: '轮胎鼓包要注意，高速爆胎风险高'},
                    {msg: '刹车片接近磨损警戒线一定要更换!'},
                    {msg: '城市道路行驶时，请勿乱开远光灯'}
                ]
            }
        },
        onLoad() {
            let self = this;
            self.notice = self.msgs[0].msg;
            setInterval(function(){
                self.count++;
                if(self.count === self.msgs.length){
                    self.count = 0;
                }
                self.notice = self.msgs[self.count].msg;
            }, 3000);

            uni.request({
                url: this.apiServier + '/fwlx/load',
                success: function (res) {
                    self.fws = res.data;
                }
            });
        },
        methods: {
            change(e) {
                this.current = e.detail.current;
            },
            getImgUrl(icon){
                return require('../../static/'+icon);
            }
        }
    }
</script>

<style scoped>
.image{
    height: 150px;
}
.index-header{
    width: 100%;
    height: 80px;
    background-position: bottom right;
    background-repeat: no-repeat;
    background-size: auto 80px;
    padding-top: 10px;
}
.header-warn{
    height: 20px;
    line-height: 20px;
    font-size: 13px;
    margin-left: 10px;
}
.scroll{
    overflow: hidden;
    white-space: nowrap;
    height: 100px;
    width: 100%;
    margin-bottom: 20px;
}
.store-server-item{
    display: inline-block;
    width: 60px;
    height: 90px;
    margin-left: 10px;
}
.store-server-item:last-child {
    margin-right: 10px;
}
.store-server-pic{
    width: 50px;
    height: 50px;
    float: left;
    margin: 20px 5px 0px 5px;
}
.store-server-txt{
    width: 60px;
    height: 20px;
    line-height: 20px;
    font-size: 12px;
    float: left;
    text-align: center;
}
.car-tips{
    width: 100%;
    height: 120px;
    background: #f2f2f2;
    position: relative;
}
.car-tips-body{
    top: 15px;
    right: 15px;
    bottom: 15px;
    left: 15px;
    background: #fff;
    position: absolute;
}
.car-tips-body-l{
    width: 60%;
    height: 100%;
    float: left;
    margin-left: 10px;
}
.car-tips-body-r{
    width: 30%;
    height: 100%;
    float: right;
    margin-right: 10px;
}
.car-tips-txt1{
    height: 20px;
    line-height: 20px;
    font-size: 12px;
    margin-top: 10px;
}
.car-tips-txt2{
    height: 20px;
    line-height: 20px;
    font-size: 10px;
    color: #5d5d5a;
}
.car-tips-btn{
    height: 30px;
    line-height: 30px;
    font-size: 11px;
    margin-top: 10px;
    border: 1px solid #ba2a34;
    color: #ba2a34;
    text-align: center;
}
.index-title{
    height: 40px;
    line-height: 40px;
    width: 100%;
}
.index-title-l{
    height: 40px;
    line-height: 40px;
    font-size: 13px;
    margin-left: 10px;
    float: left;
    color: #6b6352;
}
.index-title-r{
    height: 40px;
    line-height: 40px;
    font-size: 12px;
    margin-right: 10px;
    float: right;
    color: #a5a5a5;
}
.index-img{
    width: 94%;
    height: 160px;
    margin-left: 3%;
}
.notice-bar{
    width: 100%;
    height: 16px;
    margin-top: 10px;
}
.notice-bar-icon{
    width: 16px;
    height: 16px;
    float: left;
}
.notice-bar-msg{
    height: 16px;
    line-height: 16px;
    font-size: 9px;
    float: left;
    color: #b6b6b3;
    margin-left: 3px
}
</style>