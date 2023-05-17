<template>
  <div class="px-6 py-6 pr-sm-0">
    <!-- <div>
      <v-btn icon light>
        <v-icon>mdi-arrow-left</v-icon>
      </v-btn>
      <v-btn icon light>
        <v-icon>mdi-arrow-right</v-icon>
      </v-btn>
    </div> -->
    <v-row class="bio py-2" no-gutters>
      <v-col class="text-right px-sm-6" cols="12" sm="6">
        <h1 class="bio__name black--text">
          {{ user.name }}
        </h1>
        <h4 class="bio__dpto mb-5">
          {{ user.position }}
        </h4>
        <ul class="skills mb-5">
          <li
            v-for="skill in user.skills"
            :key="skill"
          >
            {{ skill }} -
          </li>
        </ul>
        <div v-html="user.bio"></div>
      </v-col>
      <v-col class="img_container" cols="12" sm="6">
        <img :src="user.img" alt="">
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'TeamSlider',
  props: {
    team: {
      type: Array,
      default: () => []
    }
  },
  computed: {
    user () {
      /**
        Temporary
       */
      return this.team[0] || {}
    }
  }
}
</script>

<style lang="scss" scoped>
.bio {
  color: #454647;
  &__name, &__dpto {
    line-height: 1.2;
  }
  &__dpto {
    font-weight: 400;
    color: #454647;
  }
  .skills {
    li {
      list-style-type: none;
      padding: 0.1em;
      position: relative;
      line-height: 1;
      font-size: 0.9rem;
      color: #646464;
      // font-style: italic;

      // &::after {
      //   content: "";
      //   position: absolute;
      //   right: 0;
      //   bottom: 2px;
      //   width: 1em;
      //   height: 2px;
      //   background: rgba(0,0,0,0.4);
      // }
    }
  }
  img {
    filter: grayscale(1);
  }
}
</style>
