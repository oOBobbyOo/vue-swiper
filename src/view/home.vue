<template>
    <div class="home">
		<m-swipe swipeid="swipe01" ref="swiper" :autoplay="3000" effect="fade">
			<div class="swiper-slide" slot="swiper-con">Slide 1</div>
			<div class="swiper-slide" slot="swiper-con">Slide 2</div>
			<div class="swiper-slide" slot="swiper-con">Slide 3</div>
		</m-swipe> 
    </div>
</template>

<script>
import swipe from '../components/swipe/swipe'

export default {
	name: 'home',
    data() {
        return {

        }
    },
    components: {
    	'm-swipe': swipe
    }
}
</script>

<style scoped>

</style>
