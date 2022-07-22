<template>
<div class="Slider">
	<carousel
	@nex="nex"
	@prev="prev"
	>
	<carousel-slide v-for="(slide,index) in slides" :key="slide" :index="index" :visibleSlide="visibleSlide"> 
	<img :src="slide.img"/>
	<h5>{{ slide.title }}</h5>
	</carousel-slide>
	</carousel>
</div>
	
</template>

<script>

import Carousel from "@/components/Carousel.vue";
import CarouselSlide from "@/components/CarouselSlide.vue";
export default {
	components: {
		Carousel ,
			CarouselSlide
		},
		data() {
			return {
				slides: [
					{ 'img': 'https://picsum.photos/id/237/600/350',
					'title':'broski'},
					{ 'img': 'https://picsum.photos/id/232/600/350' },
					{ 'img': 'https://picsum.photos/id/263/600/350' },
					{ 'img': 'https://picsum.photos/id/234/600/350' },
					{ 'img': 'https://picsum.photos/id/235/600/350' },
					{ 'img': 'https://picsum.photos/id/239/600/350' }
				],
				visibleSlide : 0,
			};
		},
		computed: {
		slideslen(){
				return this.slides.length;
			}
		},
		methods: {
			nex() {
				if(this.visibleSlide >= this.slideslen - 1) {
					this.visibleSlide = 0;
				}else {
					this.visibleSlide++;
				}
			},
			prev() {
				if (this.visibleSlide <= 0) {
					this.visibleSlide = this.slideslen - 1
				} else {
					this.visibleSlide--;
				}
			}

	},
	};
</script>

<style scoped>
.Slider{
	display:flex;
	justify-content: center;
}
	</style>