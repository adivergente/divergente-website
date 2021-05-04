<template>
  <section class="p_section audiovisual mb-6">
    <v-row class="mb-10">
      <v-col cols="12">
        <h1 class="section_title mb-8">
          AUDIOVISUAL
        </h1>
        <p>
          Capturamos el mejor ángulo, contamos las mejores historias, comunicamos de la mejor forma el mensaje que quieres dar. Generamos fotografía y filmaciones de alto nivel, la calidad y las propuestas creativas nos hacen únicos en el mercado.
        </p>
      </v-col>
      <v-col cols="12">
        <h4 class="font-weight-light mb-5">SERVICIOS</h4>
        <ul>
          <li>Paquetes fotográficos</li>
          <li>Paquetes de video</li>
          <li>Video institucional</li>
          <li>Live streaming</li>
          <li>Animación</li>
        </ul>
      </v-col>
    </v-row>
    <v-row>
      <!-- <v-col
        v-for="({ id, title, location }) in videos"
        :key="id"
        cols="12"
        sm="6"
        xl="4"
      >
        <div class="card mb-3">
          <div class="video-preview">
            <img :src="`https://img.youtube.com/vi/${id}/sddefault.jpg`" alt="" class="img-block">
            <a href="" @click.prevent="openVideo(id)">
              <div class="video-preview--button">
                <v-btn
                  fab
                >
                  <v-icon x-large>mdi-chevron-right</v-icon>
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
      </v-col> -->
      <v-col cols="12">
        <video-slider :videos="videos"></video-slider>
      </v-col>
    </v-row>
    <!-- <v-dialog v-model="dialog">
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
    </v-dialog> -->
  </section>
</template>

<script>
import VideoSlider from '@/components/VideoSlider'
export default {
  name: 'Audiovisual',
  components: {
    VideoSlider
  },
  data () {
    return {
      videos: [
        {
          title: 'Absentune - Live streaming',
          location: 'Ex Hacienda Queréndaro',
          // src: 'https://www.youtube.com/embed/EFMk_g7xby4'
          id: 'EFMk_g7xby4'
        },
        {
          title: 'Luka & Ceballos - Live streaming',
          location: 'Hotel de La Soledad',
          id: 'MxA1RFPpS8U'
        },
        {
          title: 'Soul Tonic - Live streaming',
          location: 'Hacienda Ucazanaztacua',
          id: 'uSiAGfGMUxc'
        },
        {
          title: 'Noche de Muertos - Live streaming',
          location: 'Hotel de la Soledad',
          id: 'Gg1rQkQn4bs'
        },
        {
          title: 'Bienvenidos al Hotel de La Soledad - Campaign',
          location: 'Hotel de la Soledad',
          id: 'CyqTUcJib4I'
        },
        {
          title: 'De Tour por Palacio Clavijero - Promotional',
          location: 'Morelia',
          id: 'iaT14VjqGrI'
        },
        {
          title: 'Semblanza a José María Morelos - Promotional',
          location: 'Morelia',
          id: '287lgYJ6nKY'
        }
        // {
        //   title: 'Amigos Real Matlatl - Campaing',
        //   location: 'Santiago Matatlan Oaxaca',
        //   src: 'https://www.facebook.com/plugins/video.php?href=https%3A%2F%2Fwww.facebook.com%2Fwatch%2F%3Fv%3D2550851851849148'
        // }
      ]
    }
  },
  created () {
    // this.$vuetify.theme.dark = false
  }
  // methods: {
  //   openVideo (id) {
  //     this.dialog = true
  //     this.src = `https://www.youtube.com/embed/${id}?modestbranding=1&rel=0&controls=1&autoplay=1`
  //   }
  // }
}
</script>

<style lang="scss" scoped>
.audiovisual {
  margin-top: 6rem;
}
</style>
