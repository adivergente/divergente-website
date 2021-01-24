<template>
  <section class="py_section px-12">
    <div class="nav_marker" id="contacto"></div>
    <v-row>
      <v-col>
        <h1 class="section_title white--text mb-8">
          04/ <br>
          HABLEMOS
        </h1>
        <v-form>
          <v-text-field
            label="Nombre"
            color="#FFF"
          />
          <v-text-field
            label="Correo Electronico"
            color="#FFF"
          />
          <v-textarea
            label="Mensaje"
            color="#FFF"
            auto-grow
            rows="2"
          />
          <div class="d-flex justify-space-between">
            <div class="d-inline-block">
              <a href="#" class="link">
                <v-icon small color="#ddd">mdi-plus</v-icon>
                FACEBOOK
              </a> <br>
              <a href="#" class="link">
                <v-icon small color="#ddd">mdi-plus</v-icon>
                INSTAGRAM
              </a>
            </div>
            <v-btn
              color="#f2f2f2"
              light
              tile
              :ripple="false"
            >enviar</v-btn>
          </div>
        </v-form>
      </v-col>
      <v-col>
        <div class="px-6 pt-12">
          <h2 class="white--text font-weight-medium mb-6">UBICACIÓN</h2>
          <p class="mb-12">
            Av. Lázaro Cardenas #4586 Col. Chapultepec Oriente <br> C.P. 58952 Morelia, Mich, MX
          </p>
          <div class="d-flex">
            <div class="d-inline-block">
              <h2 class="white--text font-weight-medium mb-6">TELÉFONO</h2>
              <a href="#" class="link">[443] 358 6998</a><br>
              <a href="#" class="link">[443] 358 6998</a>
            </div>
            <div class="d-inline-block pl-12">
              <h2 class="white--text font-weight-medium mb-6">EMAIL</h2>
              <a href="#" class="link">said@adivergente.com</a><br>
              <a href="#" class="link">administración@adivergente.com</a>
            </div>
          </div>
        </div>
      </v-col>
    </v-row>
  </section>
</template>

<script>
export default {
  name: 'HomeContacto'
}
</script>
<style lang="scss" scoped>
.link {
  display: inline-block;
  padding: 0.3em 0;
  transition: all 0.2s ease-out;
  &:hover {
    color: #FFF;
  }
}
</style>
