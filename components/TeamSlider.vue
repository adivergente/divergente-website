<template>
  <div class="px-6 py-6 pr-sm-0">
    <div>
      <v-btn icon light>
        <v-icon>mdi-arrow-left</v-icon>
      </v-btn>
      <v-btn icon light>
        <v-icon>mdi-arrow-right</v-icon>
      </v-btn>
    </div>
    <v-row class="bio py-2" no-gutters>
      <v-col class="text-right px-sm-6" cols="12" sm="6">
        <h1 class="bio__name black--text">
          Said Gomez
        </h1>
        <h3 class="bio__dpto mb-10">CEO Manager</h3>
        <ul class="skills mb-10">
          <li>Cordinación</li>
          <li>Administración</li>
          <li>Comunicación</li>
        </ul>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Enim quidem id quisquam veniam exercitationem itaque omnis nostrum cumque aspernatur iusto quae error unde quis incidunt recusandae ipsa velit, in molestias, minima nulla? Alias autem amet fugit hic magnam mollitia veniam totam, dignissimos quaerat? Aspernatur nisi dolore iusto quaerat, porro adipisci quasi quae architecto quod facere. Beatae numquam eveniet aut necessitatibus natus perspiciatis doloremque illum et quidem atque fuga asperiores fugit, laborum velit dolor nisi? Consectetur quidem eos illum nostrum rerum!
        </p>
      </v-col>
      <v-col class="img_container" cols="12" sm="6">
        <img src="/said.jpg" alt="">
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'TeamSlider'
}
</script>

<style lang="scss" scoped>
.bio {
  color: #454647;
  &__name, &__dpto {
    line-height: 1.2;
  }
  &__dpto {
    font-weight: 400;
    color: #454647;
  }
  .skills {
    li {
      list-style-type: none;
      padding: 0.1em;
      position: relative;

      // &::after {
      //   content: "";
      //   position: absolute;
      //   right: 0;
      //   bottom: 2px;
      //   width: 1em;
      //   height: 2px;
      //   background: rgba(0,0,0,0.4);
      // }
    }
  }
  img {
    filter: grayscale(1);
  }
}
</style>
