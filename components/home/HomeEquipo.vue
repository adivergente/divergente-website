<template>
  <section class="equipo">
    <div id="equipo" class="nav_marker"></div>
    <v-row class="w-100" no-gutters>
      <v-col cols="12" md="5">
        <h1 class="section_title white--text mb-8">
          02/ <br>
          EQUIPO
        </h1>
        <ul class="tabs columns">
          <li
            v-for="({name, text}) in links"
            :key="name"
          >
            <a
              href="#"
              class="tabs__item"
              :class="{ 'active': name === active }"
              @click.prevent="active = name"
            >
              {{ text }}
            </a>
          </li>
        </ul>
      </v-col>
      <v-col cols="12" md="7" class="white mt-3 team" :style="{ height: `${slideHeight}px` }">
        <div
          v-for="({name, data}) in teams"
          :key="name"
          class="team__slide"
        >
          <transition name="slide-translate" mode="in-out">
            <team-slider v-if="active === name" :key="name" :ref="name" :team="data"/>
          </transition>
        </div>
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
      active: 'said',
      links: [
        {
          name: 'said',
          text: 'Said'
        },
        {
          name: 'kaled',
          text: 'Kaled'
        },
        {
          name: 'majo',
          text: 'Majo'
        },
        {
          name: 'noemi',
          text: 'Noemi'
        },
        {
          name: 'alan',
          text: 'Alan'
        },
        {
          name: 'arturo',
          text: 'Arturo'
        },
        {
          name: 'juan',
          text: 'Juan'
        },
        {
          name: 'luis',
          text: 'Luis'
        }
      ],
      teams: [
        {
          name: 'said',
          data: [
            {
              name: 'Said Gomez',
              position: 'Dirección',
              skills: [
                'Emprendedor',
                'Creativo',
                'Estrategia'
              ],
              bio: `
                <p>
                  Lic. en Administración, egresado de la UMSNH con posgrado en Mercadotecnia (Universidad La Salle Morelia). Amplia experiencia en el sector turístico estatal y nacional. Representante de Tesoros de Michoacán.
                </p>
                <p>Líder emprendedor, amante de la buena música y los temas de interés.</p>
              `,
              img: '/team/said.jpg'
            }
          ]
        },
        {
          name: 'kaled',
          data: [
            {
              name: 'Kaled Gómez',
              position: 'Content Manager',
              skills: [
                'Emprendedor',
                'Creativo'
              ],
              bio: `
                <p>
                  Soy un joven estudiante y trabajador que quiere cumplir todas las metas propuestas por él y su familia, con hambre y sed de éxito para poder llevar a cabo la vida que siempre he soñado, fui nacido y criado en Morelia, Michoacán.
                </p>
              `,
              img: '/team/kaled.jpg'
            }
          ]
        },
        {
          name: 'majo',
          data: [
            {
              name: 'Majo Pantoja',
              position: 'Cordinadora Concept & Experience',
              skills: [
                'Creativa',
                'Emprendedora',
                'Organizacional'
              ],
              bio: `
                <p>
                  Lic. En administración hotelera y turística de la universidad interamericana para el desarrollo, con experiencia amplia en manejo de ventas y en organización de eventos de temática altruista y líder emprendedora, apasionada por las causas sociales.
                </p>
              `,
              img: '/team/majo.jpg'
            }
          ]
        },
        {
          name: 'luis',
          data: [
            {
              name: 'Luis Montoya',
              position: 'Content Manager',
              skills: [
                'Emprendedor',
                'Creativo'
              ],
              bio: `
                <p>
                  Soy Luis Montoya, soy estudiante de Administrador de empresas del Tec de Monterrey. De mis fortalezas puedo destacar la de tomas de decisión y estrategia. El trabajo en equipo es lo más importante para mí, me considero proactivo, lo que aumenta la eficacia en los proyectos.
                </p>
              `,
              img: '/team/luis.jpg'
            }
          ]
        },
        {
          name: 'noemi',
          data: [
            {
              name: 'Noemi Alarcon',
              position: 'Diseñadora',
              skills: [
                'Emprendedor',
                'Creativo'
              ],
              bio: `
                <p>
                  Diseñadora experta en múltiples áreas. Todas mis técnicas y enseñanzas las aplico en mis trabajos. Mi lado creativo siempre lo exploro y puedo hacer trabajos atractivos para todos. Brindo mi creatividad en todos los diseños que hago, plasmando los objetivos que tiene cada cliente. Mi experiencia laboral me ha ayudado a enfocarme y sacar lo que los clientes deseen.
                </p>
              `,
              img: '/team/noemi.jpg'
            }
          ]
        },
        {
          name: 'juan',
          data: [
            {
              name: 'Juan Calderón',
              position: 'Fotografía y Video',
              skills: [
                'Emprendedor',
                'Creativo'
              ],
              bio: `
                <p>
                  Soy Juan Calderón, estudiante de cine, apasionada por el arte, la fotografía. Me gusta siempre inovar y estar creando nuevas cosas.
                </p>
              `,
              img: '/team/juan.jpg'
            }
          ]
        },
        {
          name: 'arturo',
          data: [
            {
              name: 'Arturo Marín',
              position: 'Fotografía y Video',
              skills: [
                'Emprendedor',
                'Creativo'
              ],
              bio: `
                <p>
                  Estudiante en Arte y Producción Cinematográfica en la Universidad Vasco de Quiroga. Visionario, amante del cine y el deporte. Apoyado a ser bueno trabajando en equipo con una comunicación directa.
                </p>
              `,
              img: '/team/arturo.jpg'
            }
          ]
        },
        {
          name: 'alan',
          data: [
            {
              name: 'Alan Carrillo',
              position: 'Senior Motion Graphics Designer & Filmmaker',
              skills: [
                // 'Emprendedor',
                // 'Creativo'
              ],
              bio: `
                <p>
                  Más de 15 años creando videos y más 10 de ellos profesionalmente con enfoque empresarial y político. Emiratos Árabes, Estambul, Estados Unidos, Bélgica, Suiza, son algunos de los países que han contado con su trabajo remoto. Comisión de comunicación del movimiento #yosoy132, Campaña presidencial Evo Morales 2014 y Campaña a Gobernador de Alfredo Ramírez Bedolla 2021, son algunas de las producciones más significativas en su carrera.
                </p>
              `,
              img: '/team/alan.jpg'
            }
          ]
        }
      ],
      slideHeight: Number
    }
  },
  watch: {
    active (val) {
      setTimeout(() => {
        this.slideHeight = this.$refs[val][0].$el.clientHeight
      }, 500)
    }
  },
  mounted () {
    this.slideHeight = this.$refs[this.active][0].$el.clientHeight
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
.team {
  position: relative;
  transition: all 0.2s ease-out;
  &__slide {
    position: absolute;
    top: 0;
    left: 0;
  }
}
</style>
