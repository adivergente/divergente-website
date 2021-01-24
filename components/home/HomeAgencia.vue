<template>
  <section class="py_section px-12 black">
    <h1 class="section_title white--text mb-8">
      01/ <br>
      AGENCIA
    </h1>
    <v-row>
      <v-col cols="auto" class="links">
        <a
          v-for="({title}, i) in links"
          :key="i"
          href="#"
          class="tab_item"
          :class="{ 'active': i === active }"
          @click.prevent="active = i"
        >
          {{ title }}
        </a>
      </v-col>
      <v-col>
        <span v-for="({description}, index) in links" :key="index">
          <transition name="tab-fade" mode="out-in">
            <span class="value" v-if="active == index" :key="index">
              {{ description }}
            </span>
          </transition>
        </span>
      </v-col>
    </v-row>
  </section>
</template>

<script>
export default {
  name: 'HomeAgencia',
  data () {
    return {
      active: 0,
      links: [
        {
          title: 'MISIÓN',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Debitis quos alias vel numquam commodi est dolorem, eius facere ducimus, aliquam obcaecati assumenda! Cum dolores, suscipit voluptatibus similique ipsum veniam nsectetur adipisicing elit. Debitis quos alias vel numquam commodi est dolorem, eius facere ducimu'
        },
        {
          title: 'VISIÓN',
          description: 'Eius facere ducimus, aliquam obcaecati assumenda! Cum dolores, suscipit voluptatibus similique ipsum veniam sequi consequatur. Minima, reiciendis ut dolorem, beatae cupiditate iure tempora nsectetur adipisicing elit. Debitis quos alias vel numquam commodi est dolorem, eius facere ducimu'
        },
        {
          title: 'VALORES',
          description: 'Doluptatibus similique ipsum veniam sequi consequatur. Minima, reiciendis ut dolorem, beatae cupiditate iure tempora ensectetur adipisicing elit. Debitis quos alias vel numquam commodi est dolorem, eius facere ducimu architecto cum ipsam suscipit pariatur vero modi? Officia consequatur corporis commodi?'
        }
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
.links {
  width: 18em;
}
.value {
  position: absolute;
  // transform: translateX(10px);
}
.tab-fade-enter-active {
  transition: all 0.8s ease .3s;
}
.tab-fade-leave-active {
  transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.tab-fade-enter, .tab-fade-leave-to {
  transform: translateX(10px);
  opacity: 0;
}
// .translate_top {
//   transform: translateY(-5em);
// }
</style>
