<template>
  <div class="text" :class="{'text_accent': accent}">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'VText',
  props: {
    accent: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.text
  font-size: 14px
  line-height: 1.43
  letter-spacing: 0.01em
  color: $darkGrey
  +sm
    font-size: 12px
  &_accent
    color: $white
    text-transform: uppercase
    letter-spacing: 0.01em
    +sm
      +bold
      max-width: 50px
      text-align: center
</style>
