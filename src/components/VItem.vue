<template>
  <div
    class="v-item"
    :class="{
      'v-item_live': live,
      'v-item_battle': isBattleType,
    }"
    :is="live ? 'a': 'div'"
    :href="live ? '#' : null"
  >
    <div class="v-item__star">
      <svg viewBox="0 0 182 164" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M181.767 155.832L117.839 103.14L6.56497 164L71.1271 58.3003L0 0H113.255H182L181.767 155.832Z"
              :fill="live ? '#EA5656' : upcoming ? 'url(#paint0_linear)' : '#F9F9F9'"
        />
        <path d="M181.499 0.5L181.269 154.773L118.157 102.754L117.895 102.539L117.599 102.702L7.96753 162.663L71.5538 58.561L71.7807 58.1895L71.4441 57.9136L1.39874 0.5H113.255H181.499Z" :stroke="live ? 'none' : '#979797'" stroke-opacity="0.1"/>
        <defs>
          <linearGradient id="paint0_linear" x1="109.492" y1="63.2289" x2="64.7098" y2="182.147" gradientUnits="userSpaceOnUse">
            <stop stop-color="#F3FCFF"/>
            <stop offset="1" stop-color="#E1E5EE"/>
          </linearGradient>
        </defs>
      </svg>
    </div>
    <div class="v-item__info" v-if="!live">
      <v-title :grey-color="!live && !upcoming">{{time}}</v-title>
      <v-text>{{date}}</v-text>
    </div>
    <div class="v-item__info" v-else>
      <svg class="v-item__play-icon" viewBox="0 0 35 35" xmlns="http://www.w3.org/2000/svg">
        <path d="M14 25.375V9.625L24.5 17.5L14 25.375ZM17.5 0C15.2019 0 12.9262 0.452651 10.803 1.33211C8.67984 2.21157 6.75066 3.50061 5.12563 5.12563C1.84374 8.40752 0 12.8587 0 17.5C0 22.1413 1.84374 26.5925 5.12563 29.8744C6.75066 31.4994 8.67984 32.7884 10.803 33.6679C12.9262 34.5474 15.2019 35 17.5 35C22.1413 35 26.5925 33.1563 29.8744 29.8744C33.1563 26.5925 35 22.1413 35 17.5C35 15.2019 34.5474 12.9262 33.6679 10.803C32.7884 8.67984 31.4994 6.75066 29.8744 5.12563C28.2493 3.50061 26.3202 2.21157 24.197 1.33211C22.0738 0.452651 19.7981 0 17.5 0Z" />
      </svg>
      <v-text accent>WATCH LIVE!</v-text>
    </div>
    <v-text>{{tournamentName}}</v-text>
    <div class="v-item__content">
      <div class="v-item__logos">
        <div v-for="logo in logos" :key="logo.id" class="v-item__logos-item">
          <v-logo :src="logo.src" :name="logo.name" :small="isBattleType"/>
        </div>
      </div>
      <div v-if="bets">
        <div class="v-item__content-line">
          <v-title
            :grey-color="bets.firstTeam.result < bets.secondTeam.result"
          >
            {{bets.firstTeam.name}}
          </v-title>
          <v-title
            v-if="bets.firstTeam.result"
            :grey-color="bets.firstTeam.result < bets.secondTeam.result"
          >
            {{bets.firstTeam.result}}
          </v-title>
          <v-coef-label v-if="bets.firstTeam.coef">{{bets.firstTeam.coef}}</v-coef-label>
        </div>
        <div class="v-item__content-line">
          <v-title
            :grey-color="bets.firstTeam.result > bets.secondTeam.result"
          >
            {{bets.secondTeam.name}}
          </v-title>
          <v-title
            v-if="bets.secondTeam.result"
            :grey-color="bets.firstTeam.result > bets.secondTeam.result"
          >
            {{bets.secondTeam.result}}
          </v-title>
          <v-coef-label v-if="bets.secondTeam.coef">{{bets.secondTeam.coef}}</v-coef-label>
        </div>
      </div>
      <div class="v-item__groups" v-if="groups">
        <div>
          <div class="v-item__content-line">
            <v-title>{{groups.firstGroup.name}}</v-title>
          </div>
          <div class="v-item__content-line">
            <v-title>{{groups.secondGroup.name}}</v-title>
          </div>
        </div>
        <v-groups-label>{{groups.match}}</v-groups-label>
      </div>
      <div class="v-item__content-line v-item__content-line_bottom">
        <div class="v-item__bottom-text">
          <v-text
            v-for="(item, index) in results"
            :key="index"
          >
            {{item}}
          </v-text>
          <v-text v-if="timer">{{timer}}</v-text>
          <v-text v-if="map">{{map}}</v-text>
          <v-text v-if="system">{{system}}</v-text>
          <div v-if="winner" class="v-item__winner">
            <svg class="v-item__winner-icon" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M15.2 0.8H12.8V0H3.2V0.8H0.8C0.32 0.8 0 1.12 0 1.6V3.52C0 5.36 1.36 6.88 3.2 7.12V7.2C3.2 9.52 4.8 11.44 6.96 11.92L6.80528 12.6052C6.5683 13.6547 5.63591 14.4 4.56 14.4C4.24 14.4 3.92 14.64 3.84 14.96L3.2 16H12.8L12.16 14.96C12.08 14.64 11.76 14.4 11.44 14.4C10.3641 14.4 9.4317 13.6547 9.19472 12.6052L9.04 11.92C11.2 11.44 12.8 9.52 12.8 7.2V7.12C14.64 6.88 16 5.36 16 3.52V1.6C16 1.12 15.68 0.8 15.2 0.8ZM3.2 5.52C2.32 5.28 1.6 4.48 1.6 3.52V2.4H3.2V5.52ZM9.6 8L8 7.12L6.4 8L6.8 6.4L5.6 4.8H7.28L8 3.2L8.72 4.8H10.4L9.2 6.4L9.6 8ZM14.4 3.52C14.4 4.48 13.68 5.36 12.8 5.52V2.4H14.4V3.52Z" fill="#F2994A"/>
            </svg>
            <v-text>{{winner}}</v-text>
          </div>
        </div>
        <v-logo
          v-if="partner"
          :src="partner.logoSrc"
          :name="partner.name"
          partner
        />
      </div>
    </div>
  </div>
</template>

<script>
import VText from "@/components/typo/VText";
import VLogo from "@/components/VLogo";
import VTitle from "@/components/typo/VTitle";
import VCoefLabel from "@/components/VCoefLabel";
import VGroupsLabel from "./VGroupsLabel";

export default {
  name: 'VItem',
  components: {
    VGroupsLabel,
    VCoefLabel,
    VTitle,
    VLogo,
    VText
  },
  props: {
    isBattleType: Boolean,
    tournamentName: String,
    live: Boolean,
    upcoming: Boolean,
    time: String,
    date: String,
    logos: Array,
    bets: Object,
    groups: Object,
    timer: String,
    system: String,
    results: Array,
    map: String,
    winner: String,
    partner: Object
  }
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.v-item
  $this: &
  display: block
  text-decoration: none
  background: $white
  border: 1px solid rgba(143, 154, 157, 0.2)
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1)
  border-radius: 2px
  padding: 25px
  position: relative
  overflow: hidden
  height: 100%
  +sm
    padding: 15px
  &__star
    position: absolute
    top: 0
    right: 0
    height: 164px
    width: 182px
    +sm
      height: 134px
      width: 152px
  &__info
    position: absolute
    top: 25px
    right: 25px
    text-align: right
    +sm
      top: 15px
      right: 15px
      display: flex
      flex-direction: column
      align-items: center
  &__play-icon
    display: block
    height: 35px
    width: 35px
    fill: $white
    margin: 0 5px 9px auto
    +sm
      height: 25px
      width: 25px
      margin: 0 0 9px
  &__content
    margin-top: 120px
    +sm
      margin-top: 30px
  &__logos
    display: flex
    margin-bottom: 15px
  &__logos-item
    &:not(:last-child)
      margin-right: 15px
  &__content-line
    display: flex
    align-items: center
    justify-content: space-between
    & + &
      margin-top: 5px
      +sm
        margin-top: 0
    &_bottom
      margin-top: 10px
      +sm
        margin-top: 5px
  &__bottom-text
    display: flex
    div
      &:not(:last-child)
        margin-right: 3px
        &:after
          content: ' • '
  &__groups
    display: flex
    align-items: center
    justify-content: space-between
  &__winner
    display: flex
    align-items: center
  &__winner-icon
    height: 16px
    width: 16px
    display: flex
    margin-right: 10px
  &_live
    border-color: $red
  &_battle
    #{$this}__content
      margin-top: 140px
      +sm
        margin-top: 40px
</style>
