<template>
  <div>
    <div class="card mb-3">
      <div class="video-preview">
        <img :src="`https://img.youtube.com/vi/${src}/sddefault.jpg`" alt="" class="img-block">
        <div class="video-preview--button">
          <v-btn fab>
            <v-icon x-large>mdi-motion-play-outline</v-icon>
          </v-btn>
        </div>
        <!-- <a href="" @click.prevent="$emit('open', { src, type: 'youtube' })">
        </a> -->
      </div>
    </div>
    <div class="pl-4">
      <h4 class="font-weight-regular mb-1">
        - {{ title }}
        <template v-if="type">
          <span class="mx-3">|</span>
          <small>
            <v-icon left x-small color="#cbcbcb">mdi-map-marker</v-icon>
            {{ type }}
          </small>
        </template>
        <template v-if="location">
          <span class="mx-3">|</span>
          <small>
            <v-icon left x-small color="#cbcbcb">mdi-map-marker</v-icon>
            {{ location }}
          </small>
        </template>
      </h4>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VideoCard',
  props: {
    src: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    location: {
      type: String,
      default: ''
    },
    type: {
      type: String,
      default: ''
    }
  }
  // data () {
  //   return {
  //     dialog: false,
  //     src: ''
  //   }
  // },
  // methods: {
  //   openVideo (id) {
  //     this.dialog = true
  //     this.src = `https://www.youtube.com/embed/${id}?modestbranding=1&rel=0&controls=1&autoplay=1`
  //   }
  // }
}
</script>
