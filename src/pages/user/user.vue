<template>
    <view class="content">
        <view class="img-bg" :style="{backgroundImage: 'url(' + bg3 + ')' }">
            <view class="user-box">
                <view class="user-msg-box">
                    <image class="user-icon" :src="tb1" />
                    <view class="user-msg-txt">登录/注册 > </view>
                </view>
                <view class="user-item-box">
                    <view class="user-item-btn">
                        <view class="user-item-btn-num">0</view>
                        <view class="user-item-btn-name">优惠券</view>
                    </view>
                    <view class="user-item-btn-split"></view>
                    <view class="user-item-btn">
                        <view class="user-item-btn-num">0</view>
                        <view class="user-item-btn-name">购物车</view>
                    </view>
                    <view class="user-item-btn-split"></view>
                    <view class="user-item-btn">
                        <view class="user-item-btn-num">0</view>
                        <view class="user-item-btn-name">卡包</view>
                    </view>
                    <view class="user-item-btn-split"></view>
                    <view class="user-item-btn">
                        <view class="user-item-btn-num">0</view>
                        <view class="user-item-btn-name">车检报告</view>
                    </view>
                </view>
            </view>
        </view>
        <view class="user-car">
            <view class="user-car-bg" :style="{backgroundImage: 'url(' + bg4 + ')' }">
                <view class="user-car-title">我的爱车</view>
                <image class="user-car-add" :src="tb2"></image>
                <view class="user-car-content">
                    <view class="user-car-txt1">添加爱车信息</view>
                    <view class="user-car-txt2">体检更完整的智慧养护</view>
                </view>
            </view>
        </view>
        <view class="user-order">
            <view class="user-car-title">我的订单</view>
            <view class="user-order-box">
                <view class="user-order-item">
                    <image class="user-order-icon" :src="tb3"/>
                    <view class="user-order-text">全部订单</view>
                </view>
                <view class="user-order-item">
                    <image class="user-order-icon" :src="tb4"/>
                    <view class="user-order-text">待付款</view>
                </view>
                <view class="user-order-item">
                    <image class="user-order-icon" :src="tb5"/>
                    <view class="user-order-text">待核销</view>
                </view>
                <view class="user-order-item">
                    <image class="user-order-icon" :src="tb6"/>
                    <view class="user-order-text">评价</view>
                </view>
            </view>
        </view>
        <view class="user-appointment-title">
            <view class="user-appointment-bt1">我的预约</view>
            <view class="user-appointment-bt2">全部预约(0)</view>
        </view>
        <view class="user-appointment-content">
            <view class="user-appointment-box">
                今日没有预约
            </view>
        </view>
        <view class="user-about">
            <view class="user-about-tel">
                <view class="user-about-txt1">联系我们</view>
                <view class="user-about-txt2"> > </view>
            </view>
            <view class="user-about-hr"></view>
            <view class="user-about-tel">
                <view class="user-about-txt1">关于壳保养智慧门店</view>
                <view class="user-about-txt2"> > </view>
            </view>
        </view>
        <view class="h8"></view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                bg3: require('../../static/image/bg3.jpg'),
                tb1: require('../../static/image/icon/user.png'),
                bg4: require('../../static/image/bg2.jpg'),
                tb2: require('../../static/image/icon/icon-add.png'),
                tb3: require('../../static/image/icon/item08.png'),
                tb4: require('../../static/image/icon/item09.png'),
                tb5: require('../../static/image/icon/item10.png'),
                tb6: require('../../static/image/icon/item11.png'),
            }
        }
    }
</script>

<style scoped>
.content{
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
    background: #f5f5f5;
}
.img-bg{
    width: 100%;
    background-position: left top;
    background-repeat:  no-repeat;
    background-size: 100% 160px;
    height: 271px;
    position: relative;
}
.user-box{
    height: 141px;
    position: absolute;
    top: 115px;
    left: 15px;
    right: 15px;
    bottom: 15px;
    background: #fff;
}
.user-msg-box{
    height: 70px;
    width: 100%;
    border-bottom: 1px solid #f0ebeb;
}
.user-item-box{
    height: 70px;
    width: 100%;
    text-align: center;
}
.user-icon{
    width: 50px;
    height: 50px;
    margin: 10px;
    float: left;
}
.user-msg-txt{
    width: 80px;
    height: 20px;
    line-height: 20px;
    float: left;
    font-size: 13px;
    margin: 10px 0 0 10px;
    color: #5f5c5c;
}
.user-item-btn{
    height: 70px;
    width: 23%;
    float: left;
    color: #5f5c5c;
}
.user-item-btn:first-child {
    margin-left: 4%;
}
.user-item-btn-num{
    height: 20px;
    line-height: 20px;
    width: 100%;
    font-size: 14px;
    margin-top: 15px;
}
.user-item-btn-name{
    height: 20px;
    width: 100%;
    font-size: 10px;
}
.user-item-btn-split{
    height: 16px;
    width: 1px;
    margin-top: 27px;
    float: left;
    border-left: 1px solid #f0ebeb;
}
.user-car{
    height: 100px;
    width: 100%;
    background: #ffffff;
}
.user-car-bg{
    width: 100%;
    height: 100px;
    background-position: bottom right;
    background-repeat: no-repeat;
    background-size: auto 50px;
}
.user-car-title{
    height: 40px;
    line-height: 40px;
    margin: 10px 0 0 15px;
    font-size: 12px;
    font-weight: bold;
}
.user-car-add{
    width: 50px;
    height: 50px;
    float: left;
    margin-left: 15px;
}
.user-car-content{
    height: 40px;
    float: left;
    margin: 5px 0 0 10px;
}
.user-car-txt1{
    height: 20px;
    line-height: 20px;
    font-size: 14px;
    font-weight: bold;
}
.user-car-txt2{
    height: 20px;
    line-height: 20px;
    font-size: 11px;
    color: #eedf3c;
}
.user-order{
    height: 120px;
    margin-top: 15px;
    width: 100%;
    background: #ffffff;
}
.user-order-box{
    height: 60px;
    width: 100%;
}
.user-order-item{
    height: 60px;
    width: 25%;
    text-align: center;
    float: left;
}
.user-order-icon{
    height: 40px;
    width: 40px;
    margin: 0 auto;
}
.user-order-text{
    height: 20px;
    width: 100%;
    margin: 0 auto;
    font-size: 10px;
}
.user-appointment-title{
    height: 40px;
    width: 100%;
    color: #b2adad;
}
.user-appointment-bt1{
    height: 40px;
    line-height: 40px;
    float: left;
    margin-left: 15px;
    font-size: 13px;
}
.user-appointment-bt2{
    height: 40px;
    line-height: 40px;
    float: right;
    margin-right: 15px;
    font-size: 10px;
}
.user-appointment-content{
    height: 135px;
    width: 100%;
    position: relative;
}
.user-appointment-box{
    position: absolute;
    top: 0;
    left: 15px;
    right: 15px;
    bottom: 15px;
    background: #ffffff;
    border-left: 2px solid #ecd607;
    line-height: 120px;
    font-size: 13px;
    color: #b2adad;
}
.user-about{
    height: 121px;
    width: 100%;
    background: #ffffff;
}
.user-about-tel{
    height: 60px;
    width: 100%;
}
.user-about-hr{
    height: 1px;
    width: 94%;
    margin-left: 3%;
    background: #f0ebeb;
}
.h8{
    height: 8px;
    width: 100%;
}
.user-about-txt1{
    height: 60px;
    line-height: 60px;
    margin-left: 15px;
    float: left;
    font-size: 13px;
    color: #b2adad;
}
.user-about-txt2{
    height: 60px;
    line-height: 60px;
    margin-right: 15px;
    float: right;
    font-size: 13px;
    color: #b2adad;
}
</style>