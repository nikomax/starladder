<template>
  <div class="v-items-grid">
    <div
      v-for="item in items"
      :key="item.id"
      class="v-items-grid__item"
    >
      <v-item
        :isBattleType="item.isBattleType"
        :tournamentName="item.tournamentName"
        :live="item.live"
        :upcoming="item.upcoming"
        :time="item.time"
        :date="item.date"
        :logos="item.logos"
        :bets="item.bets"
        :groups="item.groups"
        :timer="item.timer"
        :system="item.system"
        :results="item.results"
        :map="item.map"
        :winner="item.winner"
        :partner="item.partner"
      />
    </div>
  </div>
</template>

<script>
import VItem from "@/components/VItem";
export default {
  name: 'VItemsGrid',
  components: {
    VItem
  },
  props: {
    items: {
      type: Array
    }
  }
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.v-items-grid
  display: flex
  flex-wrap: wrap
  margin: -17px
  +lg
    margin: -14px
  +xs
    margin: -6px
  &__item
    width: 25%
    padding: 17px
    +lg
      width: 33.33%
      padding: 14px
    +md
      width: 50%
    +sm
      width: 100%
    +xs
      padding: 6px
</style>
