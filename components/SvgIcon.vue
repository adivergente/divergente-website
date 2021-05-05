<template>
  <span>
    <svg
      v-if="name == 'flecha-izq'"
      class="clickeable svg-arrow left"
      version="1.1"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      x="0px" y="0px"
      viewBox="0 0 40 28"
      style="enable-background:new 0 0 40 28;"
      xml:space="preserve"
    >
      <g>
        <rect x="6" y="13" width="28" height="1.5" class="fill-on-hover" />
      </g>
      <g>
        <polyline
          points="13 8 6 14 13 20"
          fill="none"
          stroke="#cbcbcb"
          stroke-width="1.5"
          stroke-linejoin="round"
          class="stroke-on-hover"
        />
      </g>
    </svg>

    <svg
      v-if="name == 'flecha-der'"
      class="clickeable svg-arrow right"
      version="1.1"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      x="0px" y="0px"
      viewBox="0 0 40 28"
      style="enable-background:new 0 0 40 28;"
      xml:space="preserve"
    >
      <g>
        <rect x="6" y="13" width="28" height="1.5" class="fill-on-hover" />
      </g>
      <g>
        <polyline
          points="27 8 34 14 27 20"
          fill="none"
          stroke="#cbcbcb"
          stroke-width="1.5"
          stroke-linejoin="round"
          class="stroke-on-hover"
        />
      </g>
    </svg>
  </span>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: ''
    },
    width: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="sass" scoped>
span
  line-height: 1
  vertical-align: middle
.clickeable
  cursor: pointer
.social
  fill: #cbcbcb
.svg-arrow
  width: 55px
  transition: all 0.1s ease-in-out
  .fill-on-hover
    fill: #cbcbcb
  &:hover
    .fill-on-hover
      fill: $secondary-c
    .stroke-on-hover
      stroke: $secondary-c
.before-enter
  .left
    opacity: 0
    transform: translateX(43px)
    transition: transform 0.9s ease-in-out 0.3s
    .fill-on-hover
      opacity: 0
      transition: opacity 0.9s ease-in-out 0.6s
    .stroke-on-hover
      opacity: 0.75
      transition: opacity 1.35s ease-in-out 0.6s
  .right
    opacity: 0
    transform: translateX(-43px)
    transition: transform 0.9s ease-in-out 0.3s
    .fill-on-hover
      transition: opacity 0.9s ease-in-out 0.6s
      opacity: 0
    .stroke-on-hover
      opacity: 0.75
      transition: opacity 1.35s ease-in-out 0.6s

.has_transition
  .left
    opacity: 1
    transform: translateX(0)
    .fill-on-hover,
    .stroke-on-hover
      opacity: 1
  .right
    opacity: 1
    transform: translateX(0)
    .fill-on-hover,
    .stroke-on-hover
      opacity: 1
</style>
