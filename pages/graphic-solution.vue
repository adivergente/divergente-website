<template>
  <div class="margin-top-page mb-6">
    <section class="px_section mb-12">
      <v-row class="mb-8">
        <v-col cols="12">
          <h1 class="section_title mb-8">
            GRAPHIC SOLUTION
          </h1>
          <p>
            Diseñamos sueños.
          </p>
          <p>
            Creamos soluciones gráficas. Cada línea, cada color deben ser parte importante de tu marca. Nosotros te ayudamos a plasmar la imagen de tu marca o negocio por medio de la composición de tus gustos, sueños, símbolos y significados.
          </p>
        </v-col>
        <v-col cols="12">
          <h4 class="font-weight-light mb-5">SERVICIOS</h4>
          <ul class="list-row">
            <li>Branding</li>
            <li>Manual de identidad</li>
            <li>Diseño gráfico básico</li>
            <li>Aplicaciones</li>
          </ul>
        </v-col>
      </v-row>
      <!-- <v-row class="mb-8">
        <v-col cols="12">
          <h4 class="font-weight-light">CONOCE NUESTRO TRABAJO</h4>
        </v-col>
        <v-col cols="4">
          <v-divider></v-divider>
        </v-col>
      </v-row> -->
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
// import ImageCard from '@/components/ImageCard'
export default {
  name: 'GraphicSolution',
  head: {
    title: 'Graphic Solution',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Creamos soluciones gráficas. Te ayudamos a plasmar la imagen de tu marca o negocio.'
      },
      { hid: 'og:url', property: 'og:url', content: 'https://adivergente.com/graphic-solution' },
      { hid: 'og:title', property: 'og:title', content: 'Graphic Solution - Divergente' },
      { hid: 'og:description', property: 'og:description', content: 'Creamos soluciones gráficas. Te ayudamos a plasmar la imagen de tu marca o negocio.' }
    ]
  }
}
</script>

<style lang="scss" scoped>
</style>
