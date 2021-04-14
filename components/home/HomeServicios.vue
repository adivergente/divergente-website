<template>
  <section class="p_section black">
    <div id="servicios" class="nav_marker"></div>
    <h1 class="section_title white--text mb-8">
      03/ <br>
      SERVICIOS
    </h1>
    <div class="grid">
      <service-card
        v-for="({img, title}, i) in items"
        :key="i"
        :img="img"
        :title="title"
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
          img: '/socialmedia.jpg',
          title: 'SOCIAL MEDIA'
        },
        {
          img: '/graphic.jpg',
          title: 'GRAPHIC SOLUTION'
        },
        {
          img: '/code.jpg',
          title: 'DEVELOPMENT'
        },
        {
          img: '/concept.jpg',
          title: 'CONCEPT'
        },
        {
          img: '/audiovisual.jpg',
          title: 'AUDIOVISUAL'
        },
        {
          img: '/estrategia.jpg',
          title: 'STRATEGY'
        },
        {
          img: '/print.jpg',
          title: 'PRINT'
        },
        {
          img: '/epicco.jpg',
          title: 'EPIC.CO'
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
