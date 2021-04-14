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
      active: 'direccion',
      links: [
        {
          name: 'direccion',
          text: 'DIRECCIÓN'
        },
        {
          name: 'administracion',
          text: 'ADMINISTRACIÓN'
        },
        {
          name: 'creatividad',
          text: 'CREATIVIDAD'
        },
        {
          name: 'talento',
          text: 'TALENTO'
        },
        {
          name: 'estrategia',
          text: 'ESTRATEGIA'
        }
      ],
      teams: [
        {
          name: 'direccion',
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
                  Lic. en Administración, egresado de la UMSNH con posgrado en Mercadotecnia (Universidads La Salle Morelia). Amplia experiencia en el sector turístico estatal y nacional. Representante de Tesoros de Michoacán.
                </p>
                <p>Líder emprendedor, amante de la buena música y los temas de interés.</p>
              `,
              img: '/said.jpg'
            }
          ]
        },
        {
          name: 'administracion',
          data: [
            {
              name: 'Dafne Tapia',
              position: 'Administración',
              skills: [
                'Emprendedora',
                'Creativa',
                'Estrategia'
              ],
              bio: `
                <p>
                  Soy Dafne Tapia, Ing. en Gestión Empresarial, apasionada por el turismo y por crear e innovar en todos los sentidos.
                </p>
                <p>
                  Emprendedora desde 2016. Me gusta apoyar en todo momento, ver oportunidades en donde muchos ven problemas y ayudar a que las cosas siempre sean mejores para nuestros clientes y el equipo.
                </p>
              `,
              img: '/dafne.jpg'
            }
          ]
        },
        {
          name: 'creatividad',
          data: [
            {
              name: 'Oscar Mosqueda',
              position: 'Creatividad / Community Manager',
              skills: [
                'Emprendedor',
                'Creativo',
                'Estrategia'
              ],
              bio: `
                <p>
                  Mi nombre es Oscar Mosqueda. Licenciado en Ciencias de la Comunicación, comencé mi experiencia profesional en la comunicación digital en el 2013 como Project Manager pero siempre de la mano del lado creativo, brindando soluciones particulares a cada cliente de acuerdo a sus objetivos. Mimetizando el bagaje cultural de cada región para la creación de contenidos.
                </p>
              `,
              img: '/oscar.jpg'
            }
          ]
        },
        {
          name: 'talento',
          data: [
            {
              name: 'Taygette Orozco',
              position: 'Talento y Estructura',
              skills: [
                'Emprendedor',
                'Creativo',
                'Estrategia'
              ],
              bio: `
                <p>
                  Mercadologa  enfocada siempre a una mejora continua. ¿Mi mayor habilidad? el storytelling, ya que son las historias, la herramienta más poderosa para comunicar qué haces, quién eres y qué vendes, a lo largo 10 años de carrera laboral he usado este enfoque para conectar y  lograr una experiencia y satisfacción  de clientes tanto internos como externos.
                </p>
                <p>
                  Creo  firmemente en la guía de las habilidades del individuo para crear sinergia y potencializar sus  resultados.  Mi lema... "¡Keep it Simple!"
                </p>
              `,
              img: '/tay.jpg'
            }
          ]
        },
        {
          name: 'estrategia',
          data: [
            {
              name: 'Daniel Ceballos',
              position: 'Estrategia & Pauta',
              skills: [
                'Emprendedor',
                'Creativo',
                'Estrategia'
              ],
              bio: `
                <p>
                  Marketero digital altamente motivado y enfocado en el progreso. He ideado iniciativas estratégicas que han ayudado a diferentes compañías en su crecimiento digital y ventas online.
                </p>
                <p>
                  Soy solucionador de problemas capaz y consistente, hábil para priorizar y administrar proyectos con competencia.
                </p>
                <p>
                  Soy progresista y estoy en sintonía con los nuevos desarrollos en su campo. Eficaz y colaborador con fuertes talentos de gestión. Disfruto de sesiones de lluvia de ideas colectivas que permitan coordinar actividades para lograr un objetivo común.
                </p>
                <p>
                  "<i>Amor por aprender</i>"
                </p>
              `,
              img: '/daniel.jpg'
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
