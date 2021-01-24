<template>
  <div>
    <section class="home">
      <particles/>
    </section>
    <HomeAgencia/>
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
  width: 100%;
  height: 800px;
  background: url('~assets/img/img01.webp')no-repeat center;
  background-size: cover;
}
</style>
