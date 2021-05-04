<template>
  <div class="mx-2">
    <div class="card mb-3">
      <div class="video-preview">
        <img :src="`https://img.youtube.com/vi/${id}/sddefault.jpg`" alt="" class="img-block">
        <a href="" @click.prevent="openVideo(id)">
          <div class="video-preview--button">
            <v-btn
              fab
            >
              <v-icon x-large>mdi-motion-play-outline</v-icon>
            </v-btn>
          </div>
        </a>
      </div>
    </div>
    <div class="pl-4">
      <h4 class="font-weight-regular mb-1">
        {{ title }}
        <span class="mx-3">|</span>
        <small>
          <v-icon left x-small color="#cbcbcb">mdi-map-marker</v-icon>
          {{ location }}
        </small>
      </h4>

    </div>
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
export default {
  name: 'VideoCard',
  props: {
    id: {
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
    }
  },
  data () {
    return {
      dialog: false,
      src: ''
    }
  },
  methods: {
    openVideo (id) {
      this.dialog = true
      this.src = `https://www.youtube.com/embed/${id}?modestbranding=1&rel=0&controls=1&autoplay=1`
    }
  }
}
</script>
