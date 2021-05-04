<template>
  <div v-swiper:slider="options">
    <div class="swiper-wrapper">
      <div v-for="({ id, title, location }, i) in videos" :key="i" class="swiper-slide">
        <video-card
          :id="id"
          :title="title"
          :location="location"
        ></video-card>
      </div>
    </div>
    <!-- <v-btn
      class="navigation prev"
      fab
      small
      @click="prev"
    >
      <v-icon>mdi-chevron-left</v-icon>
    </v-btn>
    <v-btn
      class="navigation next"
      fab
      small
      @click="next"
    >
      <v-icon>mdi-chevron-right</v-icon>
    </v-btn> -->
  </div>
</template>

<script>
import VideoCard from '@/components/VideoCard'
import { directive } from 'vue-awesome-swiper'
import 'swiper/swiper-bundle.css'

export default {
  name: 'VideoSlider',
  directives: {
    swiper: directive
  },
  components: {
    VideoCard
  },
  props: {
    videos: {
      type: Array,
      default: () => []
    }
  },
  data () {
    return {
      options: {
        slidesPerView: 1,
        breakpoints: {
          600: {
            slidesPerView: 2
          }
        }
        // navigation: {
        //   nextEl: '.swiper-button-next',
        //   prevEl: '.swiper-button-prev'
        // }
      }
    }
  },
  methods: {
    prev () {
      this.slider.slidePrev()
    },
    next () {
      this.slider.slideNext()
    }
  }
}
</script>

<style lang="scss" scoped>
.navigation {
  position: absolute;
  top: 50%;
  margin-top: -1.2rem;
  z-index: 1;
  &.prev {
    left: 0.3rem;
  }
  &.next {
    right: 0.3rem;
  }
}
.swiper-slide {
  box-sizing: border-box;
}
.swiper-container {
  width: 100%;
  height: 100%;
  margin-left: auto;
  margin-right: auto;
}
</style>
