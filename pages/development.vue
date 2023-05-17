<template>
  <div class="margin-top-page mb-6">
    <section class="px_section mb-12">
      <v-row class="mb-8">
        <v-col cols="12">
          <h1 class="section_title mb-8">
            DEVELOPMENT
          </h1>
          <p>
            Desarrollo y tecnología.
          </p>
          <p>
            Desarrollo de la pagina web a tu medida. Pensada y diseñada para eficientar tus procesos de  compra, reserva, comunicación y por supuesto embellecer y enaltecer tu valor en el mundo  digital.
          </p>
        </v-col>
        <v-col cols="12">
          <h4 class="font-weight-light mb-5">SERVICIOS</h4>
          <ul class="list-row">
            <li>Websites</li>
            <li>Ecommerce</li>
            <li>Apps web empresariales</li>
            <li>Desarrollo móvil</li>
          </ul>
        </v-col>
      </v-row>
      <v-row class="mb-8">
        <v-col cols="12">
          <h4 class="font-weight-light">CONOCE NUESTRO TRABAJO</h4>
        </v-col>
        <v-col cols="4">
          <v-divider></v-divider>
        </v-col>
      </v-row>
      <v-row>
        <v-col
          v-for="({ title, image, url }) in items"
          :key="title"
          cols="12"
          sm="6"
          lg="4"
          xl="3"
        >
          <image-card
            :title="title"
            :src="image"
            @click.native="openImage(url, image)"
          />
        </v-col>
      </v-row>
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
        <div v-if="src.url">
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
              :src="src.url"
              title="Divergente"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
          </div>
        </div>
        <img v-else :src="src.image" alt="" class="img-block">
      </v-dialog>
    </section>
  </div>
</template>

<script>
import ImageCard from '@/components/ImageCard'
export default {
  name: 'Development',
  components: {
    ImageCard
  },
  data () {
    return {
      dialog: false,
      src: {},
      items: [
        {
          title: 'Hotel de La Soledad',
          url: 'https://hoteldelasoledad.com/',
          image: require('@/assets/img/development/hsoledad.jpg')
        },
        {
          title: 'Hotel Los Juaninos',
          url: 'https://hoteljuaninos.com.mx/',
          image: require('@/assets/img/development/juaninos.jpg')
        },
        {
          title: 'Scamol',
          // url: 'https://scamol.com/',
          image: require('@/assets/img/development/scamol.jpg')
        },
        {
          title: 'Ilforno',
          url: 'https://ilfornomorelia.com/',
          image: require('@/assets/img/development/ilforno.jpg')
        },
        {
          title: 'Dr. Habid Soto',
          url: 'https://drhabidsoto.com/',
          image: require('@/assets/img/development/drhabid.jpg')
        },
        {
          title: 'Reface',
          url: 'https://reface.com.mx/',
          image: require('@/assets/img/development/reface.jpg')
        },
        {
          title: 'Grand María',
          // url: 'https://reface.com.mx/',
          image: require('@/assets/img/development/grandmaria.jpg')
        },
        {
          title: 'Quinta María José',
          // url: 'https://reface.com.mx/',
          image: require('@/assets/img/development/qmj.jpg')
        },
        {
          title: 'Casa Don Pascual',
          url: 'https://casadonpascual.com/',
          image: require('@/assets/img/development/casadonpascual.jpg')
        },
        {
          title: 'Shokolate',
          url: 'https://shokolate.com.mx/',
          image: require('@/assets/img/development/shokolate.jpg')
        }
      ]
    }
  },
  methods: {
    openImage (url, image) {
      this.dialog = true
      this.src = { url, image }
    }
  },
  head: {
    title: 'Development',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Apoyamos al crecimiento de tu empresa a través de la implementación de tecnología.'
      },
      { hid: 'og:url', property: 'og:url', content: 'https://adivergente.com/development' },
      { hid: 'og:title', property: 'og:title', content: 'Development - Divergente' },
      { hid: 'og:description', property: 'og:description', content: 'Apoyamos al crecimiento de tu empresa a través de la implementación de tecnología.' }
    ]
  }
}
</script>

<style lang="scss" scoped>
</style>
