<template>
  <div id="particles-js"></div>
</template>

<script>
export default {
  name: 'ParticlesJS',

  mounted () {
    require('particles.js')
    this.$nextTick(() => {
      this.initParticlesJS()
    })
  },

  methods: {
    initParticlesJS () {
      /* eslint-disable */
      particlesJS('particles-js', {
        'particles': {
          'number': {
            'value': 70,
            'density': {
              'enable': true,
              'value_area': 850
            }
          },
          'color': {
            'value': '#cdcddc'
          },
          'shape': {
            'type': 'circle',
            'stroke': {
              'width': 0,
              'color': '#000000'
            },
            'polygon': {
              'nb_sides': 5
            }
          },
          'opacity': {
            'value': 0.5,
            'random': false,
            'anim': {
              'enable': false,
              'speed': 0.5,
              'opacity_min': 0.1,
              'sync': false
            }
          },
          'size': {
            'value': 3,
            'random': true,
            'anim': {
              'enable': false,
              'speed': 100,
              'size_min': 0.1,
              'sync': false
            }
          },
          'line_linked': {
            'enable': true,
            'distance': 100,
            'color': '#cdcddc',
            'opacity': 0.4,
            'width': 2
          },
          'move': {
            'enable': true,
            'speed': 2,
            'direction': 'none',
            'random': false,
            'straight': false,
            'out_mode': 'out',
            'bounce': false,
            'attract': {
              'enable': false,
              'rotateX': 600,
              'rotateY': 1200
            }
          }
        },
        'interactivity': {
          // 'detect_on': 'canvas',
          'events': {
            'onhover': {
              'enable': false,
              'mode': 'repulse'
            },
            'onclick': {
              'enable': false,
              'mode': 'push'
            },
            'resize': true
          }
          // 'modes': {
          //   'grab': {
          //     'distance': 800,
          //     'line_linked': {
          //       'opacity': 1
          //     }
          //   },
          //   'bubble': {
          //     'distance': 800,
          //     'size': 80,
          //     'duration': 2,
          //     'opacity': 0.8,
          //     'speed': 3
          //   },
          //   'repulse': {
          //     'distance': 400,
          //     'duration': 0.4
          //   },
          //   'push': {
          //     'particles_nb': 4
          //   },
          //   'remove': {
          //     'particles_nb': 2
          //   }
          // }
        },
        'retina_detect': true
      })
    }
  }

}
</script>

<style lang="scss" scoped>
#particles-js {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  z-index: 1;
  width: 100%;
  /* background: cornflowerblue; */
  // @media screen and ($tablet) {
  // }
}
</style>
