<template>
  <button
    class="v-button"
    :class="{'is-active': isActive}"
    @click="handleClick"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'VButton',
  props: {
    isActive: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    handleClick(e) {
      this.$emit('click', e)
    }
  }
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.v-button
  color: #757C84
  text-transform: uppercase
  +bold
  letter-spacing: 1.5px
  font-size: 14px
  line-height: 1.43
  padding: 20px 50px
  background-color: transparent
  border-radius: 0
  border: none
  cursor: pointer
  transition: background-color 0.3s, color 0.3s
  +xs
    font-size: 12px
    padding: 15px 25px
    line-height: 1.67
  &.is-active
    background-color: $red
    color: $white
</style>
