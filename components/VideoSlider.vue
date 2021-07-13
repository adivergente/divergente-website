<template>
  <div>
    <v-row class="mb-1">
      <v-col cols="12" class="d-flex justify-space-between pr-12">
        <h4 class="property-title">
          {{ header }}
        </h4>
        <div>
          <svg-icon name="flecha-izq" @click.native="prev"/>
          <svg-icon name="flecha-der" @click.native="next"/>
        </div>
      </v-col>
    </v-row>
    <div v-swiper:slider="options">
      <div class="swiper-wrapper">
        <div v-for="({ source, title, location, type }, i) in videos" :key="i" class="swiper-slide">
          <video-card
            :src="source"
            :title="title"
            :location="location"
            :type="type"
            @click.native="openVideo(source, type)"
          ></video-card>
        </div>
      </div>
    </div>
    <v-btn
      v-if="dialog"
      class="close"
      small
      fab
      color="grey darken-3"
      @click="dialog = false"
    >
      <v-icon>mdi-close</v-icon>
    </v-btn>
    <v-dialog v-model="dialog">
      <div class="aspect-16-9 relative">
        <div class="bg-loading">
          <v-progress-circular
            :size="70"
            indeterminate
            color="#cdcdcd"
          ></v-progress-circular>
        </div>
        <iframe
          v-if="dialog"
          :src="src"
          title="Divergente"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
    </v-dialog>
  </div>
</template>

<script>
import VideoCard from '@/components/VideoCard'
import SvgIcon from '@/components/SvgIcon'

export default {
  name: 'VideoSlider',
  components: {
    SvgIcon,
    VideoCard
  },
  props: {
    videos: {
      type: Array,
      default: () => []
    },
    header: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      dialog: false,
      src: '',
      options: {
        slidesPerView: 'auto',
        spaceBetween: 15
      }
    }
  },
  methods: {
    prev () {
      this.slider.slidePrev()
    },
    next () {
      this.slider.slideNext()
    },
    openVideo (source, type) {
      console.log(type)
      this.dialog = true
      this.src = `https://www.youtube.com/embed/${source}?modestbranding=1&rel=0&controls=1&autoplay=1`
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
  width: 40%;
}
.swiper-container {
  width: 100%;
  height: 100%;
  margin-left: auto;
  margin-right: auto;
}
.property-title {
  position: relative;
  padding-left: 3.2rem;
  font-weight: 300;
  font-style: italic;
  &:before {
    content: "";
    position: absolute;
    top: 0.6rem;
    left: 0;
    width: 2.5rem;
    height: 1px;
    background: rgba(255,255,255,0.5);
  }
}
</style>
