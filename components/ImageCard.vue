<template>
  <div>
    <div class="card mb-3">
      <div class="video-preview">
        <img :src="src" alt="" class="img-block">
        <!-- <div class="video-preview--button">
          <v-btn fab>
            <v-icon x-large>mdi-motion-play-outline</v-icon>
          </v-btn>
        </div> -->
      </div>
    </div>
    <div class="pl-4">
      <h4 class="font-weight-regular mb-1">
        - {{ title }}
        <!-- <template v-if="url">
          <span class="mx-3">|</span>
          <small class="d-inline-block pb-1">
            <v-icon left x-small color="#cbcbcb" class="mb-1">mdi-link</v-icon>
            <a :href="url" target="_blank">Visit website</a>
          </small>
        </template> -->
      </h4>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ImageCard',
  props: {
    title: {
      type: String,
      default: ''
    },
    src: {
      type: String,
      default: ''
    }
    // url: {
    //   type: String,
    //   default: ''
    // }
  }
}
</script>
