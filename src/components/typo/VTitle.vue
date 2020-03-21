<template>
  <div
    class="title"
    :class="`
      title_${type}
      ${greyColor ? 'title_grey' : ''}
    `"
    :is="type"
  >
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'VTitle',
  props: {
    type: {
      type: String,
      default: 'h5'
    },
    greyColor: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.title
  +bold
  &_h1
    font-size: 100px
    line-height: 1
    color: $white
    +sm
      font-size: 48px
  &_h5
    font-size: 24px
    line-height: 1.46
    color: $black
  &_grey
    color: $darkGrey

</style>
