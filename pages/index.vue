<template>
  <div>
    <section class="home px-12">
      <div class="home__title">
        <h3>Pensamiento</h3>
        <h2>DIVERGENTE</h2>
        <p>"Proceso que se sigue cuando se quieren <strong>crear</strong><br>ideas <strong>distintas</strong> para resolver un problema."</p>
      </div>
      <particles/>
    </section>
    <HomeAgencia/>
    <HomeEquipo/>
    <HomeServicios/>
    <HomeContacto/>
  </div>
</template>

<script>
import Particles from '../components/Particles'
export default {
  components: {
    Particles
  }
}
</script>
<style lang="scss" scoped>
.home {
  position: relative;
  width: 100%;
  height: 800px;
  display: flex;
  align-items: center;
  // justify-content: center;
  background: url('~assets/img/bg04.jpg')no-repeat center;
  // filter: grayscale(1);
  background-size: cover;
  &__title {
    position: relative;
    line-height: 1;
    color: #e2e2e2;
    // border: 1px solid rgba(255,255,255,0.3);
    padding: 0.8rem;
    h3 {
      font-size: 1.2rem;
      font-weight: normal;
      font-style: italic;
      @media screen and ($tablet) {
        font-size: 1.5rem;
      }
    }
    h2 {
      font-size: 3rem;
      margin-bottom: 0.5rem;
      @media screen and ($tablet) {
        font-size: 3.5rem;
      }
    }
    p {
      // width: 40%;
      text-align: right;
      font-size: 1rem;
      color: $text;
      font-weight: 300;
      // font-style: italic;
      padding-left: 1.5rem;
      strong {
        color: #f2f2f2;
      }
      // border: 1px solid white;
    }
    &::before {
      content: "";
      position: absolute;
      top: -1rem;
      left: 3rem;
      // width: 100%;
      right: 0;
      height: 100%;
      border: 1px solid rgba(255,255,255,0.3);
    }
  }
  &::before {
    content: "";
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    top: 0;
    background: rgba(0,0,0,0.65);
    // z-index: 0;
  }
}
</style>
