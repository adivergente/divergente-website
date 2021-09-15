<template>
  <div class="margin-top-page mb-6">
    <section class="px_section mb-12">
      <v-row>
        <v-col cols="12">
          <h1 class="section_title mb-8">
            AUDIOVISUAL
          </h1>
          <p>
            Capturamos el mejor ángulo, contamos las mejores historias, comunicamos de la mejor forma el mensaje que quieres dar.
          </p>
          <p>
            Generamos fotografía y filmaciones de alto nivel, la calidad y las propuestas creativas nos hacen únicos en el mercado.
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
    <section class="px_section mb-12 py-12">
      <v-row>
        <v-col
          cols="12"
        >
          <img
            v-for="i in 7"
            :key="i"
            :src="require(`~/assets/img/photo/book_page-000${i}.jpg`)" alt=""
            class="w-100"
          >
          <img
            v-for="i in 9"
            :key="i"
            :src="require(`~/assets/img/photo/pp_page-000${i}.jpg`)" alt=""
            class="w-100"
          >
          <img
            :src="require('~/assets/img/photo/pp_page-0010.jpg')" alt=""
            class="w-100"
          >
          <!-- <img
            :src="require('~/assets/img/photo/book_page-0008.jpg')" alt=""
            class="w-100"
          > -->
          <img
            :src="require(`~/assets/img/photo/pp_page-0011.jpg`)" alt=""
            class="w-100"
          >
        </v-col>
      </v-row>
    </section>
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
      ]
    }
  },
  created () {
    // this.$vuetify.theme.dark = false
  },
  // methods: {
  //   openVideo (id) {
  //     this.dialog = true
  //     this.src = `https://www.youtube.com/embed/${id}?modestbranding=1&rel=0&controls=1&autoplay=1`
  //   }
  // },
  head: {
    title: 'Audiovisual',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Capturamos el mejor ángulo, contamos las mejores historias, comunicamos de la mejor forma el mensaje que quieres dar.'
      },
      { hid: 'og:url', property: 'og:url', content: 'https://adivergente.com/audiovisual' },
      { hid: 'og:title', property: 'og:title', content: 'Audiovisual - Divergente' },
      { hid: 'og:description', property: 'og:description', content: 'Capturamos el mejor ángulo, contamos las mejores historias, comunicamos de la mejor forma el mensaje que quieres dar.' }
    ]
  }
}
</script>

<style lang="scss" scoped>
</style>
