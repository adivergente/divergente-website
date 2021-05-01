<template>
  <div class="service">
    <div class="img_container service__image">
      <div class="overlay">
        <v-btn
          fab
          small
          :ripple="false"
          :to="to"
        >
          <v-icon small>mdi-plus</v-icon>
        </v-btn>
      </div>
      <img :src="img" alt="">
    </div>
    <h2 class="subtitle-1 service__title">
      {{ title }}
    </h2>
  </div>
</template>

<script>
export default {
  name: 'ServiceCard',
  props: {
    img: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    to: {
      type: String,
      default: '/'
    }
  }
}
</script>

<style lang="scss" scoped>
.service {
  &__image {
    position: relative;
    height: 400px;
    img {
      filter: grayscale(1);
      // transition: all 0.3s ease-out;
    }
    .overlay {
      display: flex;
      justify-content: center;
      align-items: center;
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
      background: rgba(0,0,0,0.2);
      z-index: 1;
      opacity: 0;
      transition: all 0.3s ease-out;
    }
  }
  &__title {
    transition: all 0.2s ease-out;
    cursor: pointer;
  }
  &:hover {
    img {
      filter: grayscale(0);
    }
    .overlay {
      opacity: 1;
    }
    .service__title {
      color: #FFF;
    }
  }
}
</style>
