<template>
  <section class="equipo">
    <div id="equipo" class="nav_marker"></div>
    <v-row class="w-100" no-gutters>
      <v-col cols="12" md="5">
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
      <v-col cols="12" md="7" class="white mt-3">
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
.equipo {
  padding-left: 1.5em;
  padding-top: 3em;
  padding-bottom: 3em;
  @media screen and ($tablet) {
    padding-left: 3.5em;
  }
}
</style>
