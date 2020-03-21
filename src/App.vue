<template>
  <div id="app">
    <the-hero/>
    <v-tabs/>
  </div>
</template>

<script>

import TheHero from "@/components/TheHero";
import VTabs from "@/components/VTabs";

export default {
  name: 'App',
  components: {
    VTabs,
    TheHero
  },
}
</script>

<style lang="sass">
@import '@/assets/sass/index'

</style>
