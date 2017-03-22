<template>
    <div class="swiper-container" :class="swipeid">
        <div class="swiper-wrapper">
            <slot name="swiper-con"></slot>
        </div>
        <!-- 分页器 -->
        <div :class="{'swiper-pagination':pagination}"></div>
    </div>
</template>

<script>
import './swiper.js'

export default {
    props: {
        swipeid: {
            type: String,
            default: ''
        },
        effect: {
            type: String,
            default: 'slide'
        },
        loop: {
            type: Boolean,
            default: true
        },
        direction: {
            type: String,
            default: 'horizontal'
        },
        pagination: {
            type: Boolean,
            default: true
        },
        autoplay: {
            type: Number,
            default: 5000,
        },
        paginationType: {
            type: String,
            default: 'bullets'
        }
    },
    mounted() {
        var That = this;
        new Swiper('.' + That.swipeid, {
            //循环
            loop: That.loop,
            //分页器
            pagination: '.swiper-pagination',
            //分页类型
            paginationType: That.paginationType, //fraction,progress,bullets
            //自动播放
            autoplay: That.autoplay,
            //方向
            direction: That.direction,
            //特效
            effect: That.effect, //slide,fade,coverflow,cube
            //用户操作swiper之后，是否禁止autoplay
            autoplayDisableOnInteraction: false,
            //修改swiper自己或子元素时，自动初始化swiper
            observer: true, 
            //修改swiper的父元素时，自动初始化swiper
            observeParents: true
        })
    },
    data() {
        return {

        }
    }
}
</script>

<style>
@import './swiper.css';

body {
    background: #eee;
    font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
    font-size: 14px;
    color:#000;
    margin: 0;
    padding: 0;
}
.swiper-container {
    width: 500px;
    height: 300px;
    margin: 20px auto;
}
.swiper-slide {
    text-align: center;
    font-size: 18px;
    background: #fff;
    display: -webkit-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    -webkit-justify-content: center;
    justify-content: center;
    -webkit-box-align: center;
    -ms-flex-align: center;
    -webkit-align-items: center;
    align-items: center;
}
.swiper-pagination-bullet-active {
	background: #f00;
}
</style>
