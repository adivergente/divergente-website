<template>
  <section class="p_section black">
    <div id="servicios" class="nav_marker"></div>
    <h1 class="section_title mb-8">
      03/ <br>
      SERVICIOS
    </h1>
    <div class="grid">
      <service-card
        v-for="({img, title, to}, i) in items"
        :key="i"
        :img="img"
        :title="title"
        :to="to"
      />
    </div>

    <v-row>
      <v-col>
      </v-col>
    </v-row>
  </section>
</template>

<script>
export default {
  name: 'HomeServicios',
  data () {
    return {
      items: [
        {
          img: '/img/socialmedia.jpg',
          title: 'SOCIAL MEDIA',
          to: '/'
        },
        {
          img: '/img/graphic.jpg',
          title: 'GRAPHIC SOLUTION',
          to: '/'
        },
        {
          img: '/img/code.jpg',
          title: 'DEVELOPMENT',
          to: '/development'
        },
        {
          img: '/img/concept.jpg',
          title: 'CONCEPT',
          to: '/'
        },
        {
          img: '/img/audiovisual.jpg',
          title: 'AUDIOVISUAL',
          to: '/audiovisual'
        },
        {
          img: '/img/estrategia.jpg',
          title: 'STRATEGY',
          to: '/'
        },
        {
          img: '/img/print.jpg',
          title: 'PRINT',
          to: '/'
        },
        {
          img: '/img/experience.jpg',
          title: 'EXPERIENCE',
          to: '/'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2.5em 0.8em;
  @media screen and ($desktop) {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
