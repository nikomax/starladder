<template>
  <div class="v-container">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'VContainer'
}
</script>

<style lang="sass">
.v-container
  margin: 0 auto
  max-width: 1490px
  padding: 0 20px
</style>
