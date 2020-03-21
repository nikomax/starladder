<template>
  <div class="v-groups-label">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'VGroupsLabel'
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.v-groups-label
  +bold
  font-size: 14px
  line-height: 1.43
  color: $darkGrey
  letter-spacing: 0.06em
  text-transform: uppercase
  background: $lightGrey
  white-space: nowrap
  padding: 10px 15px
  border-radius: 4px
  +sm
    font-size: 12px
</style>
