<template>
  <section class="py_section pl-12">
    <div class="nav_marker" id="equipo"></div>
    <v-row>
      <v-col cols="5">
        <h1 class="section_title white--text mb-8">
          02/ <br>
          EQUIPO
        </h1>
        <ul class="tabs">
          <li
            v-for="(link, i) in links"
            :key="i"
            href="#"
          >
            <a
              href="#"
              class="tabs__item"
              :class="{ 'active': i === active }"
              @click.prevent="active = i"
            >
              {{ link }}
            </a>
          </li>
        </ul>
      </v-col>
      <v-col cols="7" class="white mt-3">
        <team-slider/>
      </v-col>
    </v-row>
  </section>
</template>

<script>
import TeamSlider from '@/components/TeamSlider'
export default {
  name: 'HomeEquipo',
  components: {
    TeamSlider
  },
  data () {
    return {
      active: 0,
      links: [
        'CEO',
        'MANAGMENT',
        'CREATIVE',
        'DESIGN',
        'STRATEGY'
      ]
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
