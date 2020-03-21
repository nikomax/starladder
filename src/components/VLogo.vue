<template>
  <div
    class="v-logo"
    :class="{
      'v-logo_partner': partner,
      'v-logo_small': small,
    }"
  >
    <img class="v-logo__image" :src="src" :alt="name">
  </div>
</template>

<script>
export default {
  name: 'VLogo',
  props: {
    src: {
      type: String,
      required: true
    },
    name: {
      type: String,
      default: 'Logo'
    },
    partner: {
      type: Boolean,
      default: false
    },
    small: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.v-logo
  height: 50px
  width: 50px
  +sm
    height: 40px
    width: 40px
  &__image
    display: block
    height: 100%
    width: 100%
    object-fit: contain
  &_partner
    max-height: 20px
    max-width: 62px
    height: auto
    width: auto
  &_small
    height: 30px
    width: 30px
</style>
