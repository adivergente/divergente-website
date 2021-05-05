<template>
  <div class="audiovisual mb-6">
    <section class="px_section mb-12">
      <v-row class="mb-8">
        <v-col cols="12">
          <h1 class="section_title mb-8">
            DEVELOPMENT
          </h1>
          <p>
            Desarrollamos tecnología.
          </p>
          <p>
            Apoyamos al crecimiento de tu empresa a través de la implementación de tecnología y ofrecemos soluciones eficientes que permiten optimizar procesos y  mostrar a tus clientes los productos y/o  servicios que ofreces.
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
  name: 'Audiovisual',
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
          url: 'http://hoteljuaninos.com.mx/',
          image: require('@/assets/img/development/juaninos.jpg')
        },
        {
          title: 'Scamol',
          url: 'http://scamol.com/',
          image: require('@/assets/img/development/scamol.jpg')
        },
        {
          title: 'Ilforno',
          url: 'https://ilfornomorelia.com/',
          image: require('@/assets/img/development/ilforno.jpg')
        },
        {
          title: 'Dr. Habid Soto',
          url: 'http://drhabidsoto.com/',
          image: require('@/assets/img/development/drhabid.jpg')
        },
        {
          title: 'Reface',
          url: 'http://reface.com.mx/',
          image: require('@/assets/img/development/reface.jpg')
        },
        {
          title: 'Grand María',
          // url: 'http://reface.com.mx/',
          image: require('@/assets/img/development/grandmaria.jpg')
        },
        {
          title: 'Quinta María José',
          // url: 'http://reface.com.mx/',
          image: require('@/assets/img/development/qmj.jpg')
        },
        {
          title: 'Casa Don Pascual',
          url: 'http://casadonpascual.com/',
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
  }
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
