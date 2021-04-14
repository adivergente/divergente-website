<template>
  <section class="p_section black">
    <div id="agencia" class="nav_marker"></div>
    <h1 class="section_title white--text mb-8">
      01/ <br>
      AGENCIA
    </h1>
    <v-row>
      <v-col cols="12" md="auto" class="links">
        <ul class="tabs">
          <li
            v-for="({title}, i) in links"
            :key="i"
            href="#"
          >
            <a
              href="#"
              class="tabs__item"
              :class="{ 'active': i === active }"
              @click.prevent="active = i"
            >
              {{ title }}
            </a>
          </li>
        </ul>
      </v-col>
      <v-col class="relative description">
        <span v-for="({description}, index) in links" :key="index">
          <transition name="tab-fade" mode="out-in">
            <span v-if="active == index" :key="index" class="value" v-html="description"></span>
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
          description: 'Nos enfocamos en atender los problemas y necesidades de cada cliente para poder ofrecerle soluciones y estrategias de comunicación online y offline que los ayuden a lograr objetivos específicos para potencializar su marca.'
        },
        {
          title: 'VISIÓN',
          description: 'Ofrecer los mejores productos digitales a través de las herramientas adecuadas.'
        },
        {
          title: 'VALORES',
          description: '<strong>Pasión</strong> en lo que hacemos. <br><strong>Calidad y liderazgo</strong> en cada proyecto. <br><strong>Empatía</strong> hacia los clientes y compañeros. <br> <strong>Responsabilidad</strong> para crear calidad e innovación. <br><strong>Audacia</strong> para resolver situaciones específicas.'
        }
      ]
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
  left: 0;
  // display: inline-block;
  padding: 0 12px;
  // transform: translateX(10px);
}
.description {
  min-height: 300px;
  @media screen and ($tablet) {
    min-height: 200px;
  }
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
</style>
