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
          description: 'Potencializar y llevar tu marca al siguiente nivel a través de herramientas y estrategias de  comunicación que nos permitan destacar tus fortalezas y pulir tus las zonas de oportunidad.'
        },
        {
          title: 'VISIÓN',
          description: 'Ser referente y punta de lanza en la industria del marketing, destacándonos por las ideasos mejores productos digitales a través de las herramientas ainnovadoras y ejecuciones disruptivas que generamos, marcando tendencia y generando un sello personal y único en cada proyecto.'
        },
        {
          title: 'VALORES',
          description: `
            - <strong>Pasión</strong> en los resultados. <br>
            - <strong>Calidad y liderazgo</strong> en cada proyecto. <br>
            - <strong>Velocidad</strong> en reacción y ejecución. <br>
            - <strong>Audacia</strong> para resolución de problemas. <br>
            - <strong>Atención</strong> en los detalles.
          `
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
