<template>
  <div class="menu">
    <header class="px-12" :class="{ 'fixed_nav elevation-1': fixedNav }">
      <a href="javascript:;" class="logo img_container">
        <img src="~assets/img/logo.png" alt="">
      </a>
      <nav>
        <nuxt-link to="/">INICIO</nuxt-link>
        <nuxt-link to="#agencia">AGENCIA</nuxt-link>
        <nuxt-link to="#equipo">EQUIPO</nuxt-link>
        <nuxt-link to="#servicios">SERVICIOS</nuxt-link>
        <nuxt-link to="#contacto">CONTACTO</nuxt-link>
      </nav>
    </header>
    <v-btn
      small
      fab
      color="grey darken-3"
      dark
      class="btn_fixed anim"
      :class="{ 'btn_fixed__show': showBtn }"
      :ripple="false"
      @click="goTop"
    >
      <v-icon>mdi-chevron-up</v-icon>
    </v-btn>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      showBtn: false,
      fixedNav: false
    }
  },
  beforeMount () {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      this.fixedNav = window.scrollY > 100 || false
      this.showBtn = window.scrollY > window.innerHeight / 2 || false
    },
    goTop () {
      window.scroll({ top: 0 })
      if (this.$route.name === 'index') {
        this.$router.replace('/').catch(err => err)
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.menu {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 100px;
  z-index: 10;
  .fixed_nav {
    position: fixed;
    left: 0;
    padding-top: 0.8rem;
    padding-bottom: 0.8rem;
    background: #000;
    transform: translateY(-100%);
    animation: menu .3s linear 0.3s forwards;
    .logo {
      width: 3.5rem;
    }
  }
}
@keyframes menu {
  to {
    transform: translateY(0);
  }
}
header {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 1.3rem;
  padding-bottom: 1.3rem;
}
nav {
  display: flex;
  align-items: center;
  justify-content: center;
  a {
    padding: 0 1em;
    color: #f2f2f2;
    // text-shadow: 1px 1px 12px rgba(0, 0, 0, 0.7);
    transition: all 0.2s ease-out;
    font-weight: 300;
    font-size: 1.1em;
    &:hover, &.nuxt-link-exact-active {
      color: #aaa;
    }
  }
}
.logo {
  width: 6rem;
  transition: all 0.2s ease-out;
}
.btn_fixed {
  position: fixed;
  bottom: 15px;
  right: 15px;
  opacity: 0;
  transition: all 0.8s ease-out;
  &__show {
    opacity: 1;
  }
}
</style>
