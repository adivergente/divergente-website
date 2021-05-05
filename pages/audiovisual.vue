<template>
  <div class="audiovisual mb-6">
    <section class="px_section mb-12">
      <v-row>
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
          <ul class="list-row">
            <li>Paquetes fotográficos</li>
            <li>Paquetes de video</li>
            <li>Video institucional</li>
            <li>Live streaming</li>
            <li>Animación</li>
          </ul>
        </v-col>
        <!-- <v-col cols="6">
          <v-divider class="my-6"></v-divider>
        </v-col> -->
      </v-row>
    </section>
    <div
      v-for="({ title, videos }, index) in items"
      :key="index"
      class="pl_section py-10"
      :class="{ 'black': index % 2 === 0 }"
    >
      <v-row>
        <v-col cols="12">
          <video-slider
            :videos="videos"
            :header="title"
          />
        </v-col>
      </v-row>
    </div>
  </div>
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
      items: [
        {
          title: 'Hotel de La Soledad',
          videos: [
            {
              source: 'Gg1rQkQn4bs',
              title: 'Noche de Muertos',
              // location: 'Hotel de la Soledad',
              type: 'Live Streaming'
            },
            {
              source: 'CyqTUcJib4I',
              title: 'Bienvenidos al Hotel de La Soledad ',
              // location: 'Hotel de la Soledad',
              type: 'Campaing'
            },
            {
              source: 'iaT14VjqGrI',
              title: 'De Tour por Palacio Clavijero',
              // location: 'Morelia',
              type: 'Promotional'
            },
            {
              source: '287lgYJ6nKY',
              title: 'Semblanza a José María Morelos',
              // location: 'Morelia',
              type: 'Promotional'
            }
          ]
        }
        // {
        //   title: 'Real Matlatl',
        //   videos: [
        //     {
        //       id: '287lgYJ6nKY',
        //       title: 'Semblanza a José María Morelos - Promotional',
        //       location: 'Morelia'
        //     }
        //   ]
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
  margin-top: 9rem;
}
.list-row {
  display: flex;
  padding-left: 0;
  li {
    margin-left: 2rem;
    &:first-child {
      margin-left: 1rem;
    }
  }
}
</style>
