<template>
    <view class="img-bg" :style="{backgroundImage: 'url(' + bg2 + ')' }">
        <view class="content-body">
            <view class="content-head">
                <view class="content-title">{{title}}</view>
                <image class="content-send" :src="tb01"></image>
            </view>
            <view class="content-head">
                <image class="store-rate" :src="tb03"></image>
                <text class="content-title store-rate-text" style="margin-left: 3px;">5.0</text>
                <text class="content-title store-rate-text" style="margin-left: 20px;">{{pjs}}条评论></text>
                <image class="store-logo" :src="tb02"></image>
            </view>
            <view class="store-img-item">
                <view class="store-img-body">
                    <image class="store-img" :src="tb04"></image>
                    <view class="store-img-text">
                        <text class="store-img-text-l">门店环境</text>
                        <text class="store-img-text-r">2</text>
                    </view>
                </view>
                <view class="store-img-body">
                    <image class="store-img" :src="tb04"></image>
                    <view class="store-img-text">
                        <text class="store-img-text-l">门店资质</text>
                        <text class="store-img-text-r">1</text>
                    </view>
                </view>
                <view class="store-img-body">
                    <image class="store-img" :src="tb04"></image>
                    <view class="store-img-text">
                        <text class="store-img-text-l">门店设备</text>
                        <text class="store-img-text-r">2</text>
                    </view>
                </view>
            </view>
            <view class="store-explain-body">
                <view class="store-explain-item">汽车轮胎</view>
                <view class="store-explain-item">汽车用品</view>
                <view class="store-explain-item">汽车保养</view>
                <view class="store-explain-item">汽车维修</view>
            </view>
            <view class="store-time-body">
                <image class="store-time-tb" :src="tb05"></image>
                <view class="store-time-txt">{{place}}</view>
                <image class="store-time-btn" :src="tb06"></image>
            </view>
            <view style="width: 94%; height: 1px; background: #f4efef; margin-left: 3%;"></view>
            <view class="store-time-body">
                <image class="store-time-tb" :src="tb07"></image>
                <view class="store-time-txt">{{time}}</view>
                <image class="store-time-btn" :src="tb08"></image>
            </view>
            <view class="store-goods-body">
                <view class="store-goods-title">爆品推荐</view>
                <scroll-view scroll-x="true" class="scroll">
                    <view class="store-goods-item" v-for="goods  in fireGoods">
                        <image class="store-goods-pic" :src="goods.url"></image>
                        <view class="store-goods-txt">{{goods.name}}</view>
                        <view class="store-goods-price">￥{{goods.price}}</view>
                    </view>
                </scroll-view>
            </view>
            <view class="store-rate-body">
                <uniEvaluate :isShowIcon="isShowIcon" :list-data="evaluateData" :rate="rateData" />
            </view>
            <view class="store-app-explain">
                <view class="store-app-explain-tt">免责声明：</view>
                <view class="store-app-explain-bb">门店信息由门店发布，具体信息以门店实际为准，平台只负责展示、发布。</view>
            </view>
        </view>
    </view>
</template>
<script>
    import uniEvaluate from "@/components/xiujun-evaluate/uni-evaluate.vue"

    export default {
        components: {
            uniEvaluate
        },
        data () {
            return {
                bg2: require('../../static/image/bg1.jpg'),
                title: '阿玉汽车保养',
                tb01: require('../../static/image/icon/icon-send.png'),
                tb02: require('../../static/image/store/store-logo.png'),
                rateData: 5,
                isShowIcon: false,
                evaluateData: [
                    {
                        user_name: "一个麻瓜",
                        header_img: require('../../static/image/icon/icon-send.png'),
                        rate: 5,
                        create_time: "2019-04-12",
                        content: "好评"
                    },
                    {
                        user_name: "哈哈哈",
                        header_img: require('../../static/image/icon/icon-send.png'),
                        content: "中评",
                        create_time: "2019-04-12",
                        rate: 4
                    },
                    {
                        user_name: "神采焕发",
                        header_img: require('../../static/image/icon/icon-send.png'),
                        content: "中评",
                        create_time: "2019-04-12",
                        rate: 4
                    }
                ],
                tb03: require('../../static/image/store/store-rate.png'),
                pjs: 0,
                tb04: require('../../static/image/store/tp1.jpg'),
                tb05: require('../../static/image/icon/icon-position.png'),
                tb06: require('../../static/image/icon/icon-place.png'),
                tb07: require('../../static/image/icon/icon-clock.png'),
                tb08: require('../../static/image/icon/icon-phone.png'),
                place: '郑州市二七区航海路升龙城',
                time: '今日营业时间 07:30-19:00',
                fireGoods: [
                    {
                        url: require('../../static/image/2.jpg'),
                        name: '壳牌金装极净超凡喜力机油',
                        price: '738.00'
                    },{
                        url: require('../../static/image/3.jpg'),
                        name: '精致洗车',
                        price: '88.00'
                    },{
                        url: require('../../static/image/4.jpg'),
                        name: '普通洗车',
                        price: '40.00'
                    }
                ]
            }
        },
        methods: {

        }
    }
</script>

<style scoped>
    .img-bg{
        width: 100%;
        background-position: left top;
        background-repeat:  no-repeat;
        background-size: 100% auto;
        padding-top: 130px;
    }
    .content-body{
        width: 100%;
        background: #ffffff;
        border-radius: 20px 20px 0 0;
        padding-top: 10px;
    }
    .content-head{
        width: 100%;
        height: 30px;
    }
    .content-title{
        height: 30px;
        line-height: 30px;
        font-size: 14px;
        margin-left: 10px;
        float: left;
    }
    .content-send{
        height: 30px;
        width: 30px;
        float: right;
        margin-right: 10px;
    }
    .store-logo{
        height: 20px;
        width: 70px;
        float: right;
        margin-right: 10px;
        margin-top: 5px;
    }
    .store-rate{
        height: 20px;
        width: 80px;
        float: left;
        margin-left: 10px;
        margin-top: 5px;
    }
    .store-rate-text{
        font-size: 12px;
        color: #808080;
    }
    .store-img-item{
        width: 100%;
        height: 70px;
        margin-top: 20px;
    }
    .store-img-body{
        width: 30%;
        height: 70px;
        margin-left: 2.5%;
        float: left;
        position: relative;
    }
    .store-img{
        width: 100%;
        height: 100%;
    }
    .store-img-text{
        width: 100%;
        height: 20px;
        line-height: 20px;
        position: absolute;
        bottom: 0px;
        left: 0px;
        font-size: 10px;
        background: rgba(0,0,0,0.3);
        color: #ffffff;
    }
    .store-img-text-l{
        float: left;
        margin-left: 8px;
    }
    .store-img-text-r{
        float: right;
        margin-right: 8px;
    }
    .store-explain-body{
        width: 100%;
        height: 20px;
        margin-top: 4px;
    }
    .store-explain-item{
        float: left;
        margin-left: 8px;
        background: #f2f0f0;
        width: 50px;
        height: 20px;
        line-height: 20px;
        text-align: center;
        color: #b8b4b4;
        font-size: 10px;
    }
    .store-time-body{
        width: 100%;
        height: 50px;
        margin-top: 4px;
    }
    .store-time-tb{
        width: 16px;
        height: 16px;
        margin-top: 17px;
        float: left;
        margin-left: 10px;
    }
    .store-time-txt{
        height: 50px;
        line-height: 50px;
        margin-left: 5px;
        font-size: 13px;
        float: left;
    }
    .store-time-btn{
        width: 30px;
        height: 30px;
        margin-top: 10px;
        float: right;
        margin-right: 10px;
    }
    .store-goods-body{
        width: 100%;
        height: 190px;
        background: #efefef;
        padding-bottom: 10px;
    }
    .store-goods-title{
        width: 100px;
        height: 40px;
        line-height: 40px;
        color: #6b6352;
        margin-left: 10px;
        font-size: 12px;
    }
    .scroll{
        overflow: hidden;
        white-space: nowrap;
        height: 140px;
        width: 100%;
    }
    .store-goods-item{
        display: inline-block;
        width: 130px;
        height: 140px;
        margin-left: 10px;
    }
    .store-goods-item:last-child {
        margin-right: 10px;
    }
    .store-goods-pic{
        width: 130px;
        height: 90px;
        float: left;
    }
    .store-goods-txt{
        width: 130px;
        height: 30px;
        line-height: 15px;
        font-size: 10px;
        color: #6b6352;
        float: left;
    }
    .store-goods-price{
        width: 130px;
        height: 20px;
        line-height: 20px;
        font-size: 11px;
        float: left;
    }
    .store-rate-body{
        width: 100%;
        height: 250px;
        margin-top: 20px;
    }
    .store-app-explain{
        width: 100%;
        height: 60px;
        background: #efefef;
        font-size: 11px;
        color: #a5a5a5;
        padding-top: 20px;
    }
    .store-app-explain-tt{
        width: 30%;
        height: 30px;
        line-height: 15px;
        float: left;
        text-align: right;
    }
    .store-app-explain-bb{
        height: 30px;
        width: 64%;
        line-height: 15px;
        float: left;
    }
</style>