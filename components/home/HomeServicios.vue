<template>
  <section class="py_section black px-12">
    <div class="nav_marker" id="servicios"></div>
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
          img: '/socialmedia.jpg',
          title: 'GRAPHIC SOLUTION'
        },
        {
          img: '/socialmedia.jpg',
          title: 'DEVELOPMENT'
        },
        {
          img: '/socialmedia.jpg',
          title: 'CONCEPT'
        },
        {
          img: '/socialmedia.jpg',
          title: 'AUDIOVISUAL'
        },
        {
          img: '/socialmedia.jpg',
          title: 'STRATEGY'
        },
        {
          img: '/socialmedia.jpg',
          title: 'PRINT'
        },
        {
          img: '/socialmedia.jpg',
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
  grid-template-columns: repeat(4, 1fr);
  gap: 2.5em 0.8em;
}
</style>
