<template>
  <div class="the-hero">
    <v-container>
      <v-title type="h1">Make me up!</v-title>
    </v-container>
  </div>
</template>

<script>
import VContainer from "@/components/VContainer";
import VTitle from "@/components/typo/VTitle";

export default {
  name: 'TheHero',
  components: {
    VTitle,
    VContainer
  }
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.the-hero
  background-color: $black
  padding: 125px 0 135px
  background-image: url("/img/hero-desktop.jpg")
  +cover
  position: relative
  overflow: hidden
  z-index: 1
  +xs
    padding: 90px 0
  &:before
    z-index: -1
    content: ''
    background-image: url("/img/logo-star.svg")
    background-repeat: no-repeat
    background-size: 100% 100%
    position: absolute
    bottom: 0
    left: 0
    width: 390px
    height: 100%
    +sm
      display: none
</style>
