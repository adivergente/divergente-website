<template>
  <section class="p_section audiovisual">
    <h1 class="section_title mb-8">
      AUDIOVISUAL
    </h1>
  </section>
</template>

<script>
export default {
  name: 'Audiovisual',
  created () {
    this.$vuetify.theme.dark = false
  }
}
</script>

<style lang="scss" scoped>
.audiovisual {
  margin-top: 6rem;
}
</style>
