<template>
  <div class="v-coef-label">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'VCoefLabel'
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.v-coef-label
  +bold
  font-size: 14px
  line-height: 1.43
  color: $black
  letter-spacing: 0.02em
  text-transform: uppercase
  background: $lightGrey
  border: 1px solid rgba(151, 151, 151, 0.1)
  height: 24px
  width: 60px
  display: flex
  align-items: center
  justify-content: center
  +sm
    font-size: 12px
    height: 20px
    width: 55px
</style>
