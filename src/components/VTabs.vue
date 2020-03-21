<template>
  <div class="v-tabs">
    <v-container>
      <div class="v-tabs__buttons">
        <v-button
          v-for="(tab, index) in tabs"
          :key="tab.id"
          @click="changeTab(index)"
          :is-active="index === activeIndex"
        >
          {{tab.button}}
        </v-button>
      </div>
      <div class="v-tabs__content">
        <div class="v-tabs__item">
          <v-items-grid :items="tabContent"/>
        </div>
      </div>
    </v-container>
  </div>
</template>

<script>
import VContainer from "@/components/VContainer";
import VButton from "@/components/VButton";
import VItemsGrid from "@/components/VItemsGrid";

const generateId = () => `f${(~~(Math.random()*1e8)).toString(16)}`;
export default {
  name: 'VTabs',
  components: {
    VItemsGrid,
    VButton,
    VContainer
  },
  data() {
    return {
      activeIndex: 0,
      tabs: [
        {
          id: generateId(),
          button: 'MATCHES',
          content: [
            {
              id: generateId(),
              tournamentName: 'Asia Minor: Play-Off',
              live: true,
              logos: [
                {
                  id: generateId(),
                  src: '/img/team1.png',
                  name: 'team1'
                },
                {
                  id: generateId(),
                  src: '/img/team2.png',
                  name: 'team2'
                }
              ],
              bets: {
                firstTeam: {
                  name: 'Albert Warren',
                  coef: '3.22'
                },
                secondTeam: {
                  name: 'Gloria Henry',
                  coef: '53.22'
                },
              },
              system: 'Bо 3',
              partner: {
                logoSrc: '/img/partner.png',
                name: 'GG Bet'
              }
            },
            {
              id: generateId(),
              tournamentName: 'Asia Minor: Play-Off',
              upcoming: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/team1.png',
                  name: 'team1'
                },
                {
                  id: generateId(),
                  src: '/img/team2.png',
                  name: 'team2'
                }
              ],
              bets: {
                firstTeam: {
                  name: 'Ricardo Hawkins',
                  coef: '3.22'
                },
                secondTeam: {
                  name: 'Bruce Simmmons',
                  coef: '53.22'
                },
              },
              timer: 'Starts in: 5 hours 39 min',
              system: 'Bо 3',
              partner: {
                logoSrc: '/img/partner.png',
                name: 'GG Bet'
              }
            },
            {
              id: generateId(),
              tournamentName: 'Asia Minor: Play-Off',
              upcoming: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/team1.png',
                  name: 'team1'
                },
                {
                  id: generateId(),
                  src: '/img/team2.png',
                  name: 'team2'
                }
              ],
              bets: {
                firstTeam: {
                  name: 'Ricardo Hawkins',
                  coef: '3.22'
                },
                secondTeam: {
                  name: 'Bruce Simmmons',
                  coef: '53.22'
                },
              },
              timer: 'Starts in: 5 hours 39 min',
              system: 'Bо 3',
              partner: {
                logoSrc: '/img/partner.png',
                name: 'GG Bet'
              }
            },
            {
              id: generateId(),
              tournamentName: 'Asia Minor: Play-Off',
              upcoming: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/team1.png',
                  name: 'team1'
                },
                {
                  id: generateId(),
                  src: '/img/team2.png',
                  name: 'team2'
                }
              ],
              bets: {
                firstTeam: {
                  name: 'Ricardo Hawkins',
                  coef: '3.22'
                },
                secondTeam: {
                  name: 'Bruce Simmmons',
                  coef: '53.22'
                },
              },
              timer: 'Starts in: 5 hours 39 min',
              system: 'Bо 3',
              partner: {
                logoSrc: '/img/partner.png',
                name: 'GG Bet'
              }
            },
            {
              id: generateId(),
              tournamentName: 'Asia Minor: Play-Off',
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/team1.png',
                  name: 'team1'
                },
                {
                  id: generateId(),
                  src: '/img/team2.png',
                  name: 'team2'
                }
              ],
              bets: {
                firstTeam: {
                  name: 'Ricardo Hawkins',
                  result: '0'
                },
                secondTeam: {
                  name: 'Bruce Simmmons',
                  result: '3'
                },
              },
              results: ['1:0', '1:0', '1:0'],
              partner: {
                logoSrc: '/img/partner.png',
                name: 'GG Bet'
              }
            },
            {
              id: generateId(),
              tournamentName: 'Asia Minor: Play-Off',
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/team1.png',
                  name: 'team1'
                },
                {
                  id: generateId(),
                  src: '/img/team2.png',
                  name: 'team2'
                }
              ],
              bets: {
                firstTeam: {
                  name: 'Ricardo Hawkins',
                  result: '0'
                },
                secondTeam: {
                  name: 'Bruce Simmmons',
                  result: '3'
                },
              },
              results: ['1:0', '1:0', '1:0'],
              partner: {
                logoSrc: '/img/partner.png',
                name: 'GG Bet'
              }
            },
            {
              id: generateId(),
              tournamentName: 'Asia Minor: Play-Off',
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/team1.png',
                  name: 'team1'
                },
                {
                  id: generateId(),
                  src: '/img/team2.png',
                  name: 'team2'
                }
              ],
              bets: {
                firstTeam: {
                  name: 'Ricardo Hawkins',
                  result: '0'
                },
                secondTeam: {
                  name: 'Bruce Simmmons',
                  result: '3'
                },
              },
              results: ['1:0', '1:0', '1:0'],
              partner: {
                logoSrc: '/img/partner.png',
                name: 'GG Bet'
              }
            },
            {
              id: generateId(),
              tournamentName: 'Asia Minor: Play-Off',
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/team1.png',
                  name: 'team1'
                },
                {
                  id: generateId(),
                  src: '/img/team2.png',
                  name: 'team2'
                }
              ],
              bets: {
                firstTeam: {
                  name: 'Ricardo Hawkins',
                  result: '0'
                },
                secondTeam: {
                  name: 'Bruce Simmmons',
                  result: '3'
                },
              },
              results: ['1:0', '1:0', '1:0'],
              partner: {
                logoSrc: '/img/partner.png',
                name: 'GG Bet'
              }
            }
          ]
        },
        {
          id: generateId(),
          button: 'BATTLES',
          content: [
            {
              id: generateId(),
              tournamentName: 'Group Stage',
              live: true,
              isBattleType: true,
              logos: [
                {
                  id: generateId(),
                  src: '/img/p-logo.png',
                  name: 'logo'
                }
              ],
              groups: {
                firstGroup: {
                  name: 'Group A',
                },
                secondGroup: {
                  name: 'Group B',
                },
                match: 'Match #1'
              },
              map: 'Map: Erangel'
            },
            {
              id: generateId(),
              tournamentName: 'Group Stage',
              isBattleType: true,
              upcoming: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/p-logo.png',
                  name: 'logo'
                }
              ],
              groups: {
                firstGroup: {
                  name: 'Group A',
                },
                secondGroup: {
                  name: 'Group B',
                },
                match: 'Match #2'
              },
              timer: 'Starts in: 5 hours 39 min',
              map: 'Map: Erangel'
            },
            {
              id: generateId(),
              tournamentName: 'Group Stage',
              isBattleType: true,
              upcoming: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/p-logo.png',
                  name: 'logo'
                }
              ],
              groups: {
                firstGroup: {
                  name: 'Group A',
                },
                secondGroup: {
                  name: 'Group B',
                },
                match: 'Match #2'
              },
              timer: 'Starts in: 5 hours 39 min',
              map: 'Map: Erangel'
            },
            {
              id: generateId(),
              tournamentName: 'Group Stage',
              isBattleType: true,
              upcoming: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/p-logo.png',
                  name: 'logo'
                }
              ],
              groups: {
                firstGroup: {
                  name: 'Group A',
                },
                secondGroup: {
                  name: 'Group B',
                },
                match: 'Match #2'
              },
              timer: 'Starts in: 5 hours 39 min',
              map: 'Map: Erangel'
            },
            {
              id: generateId(),
              tournamentName: 'Group Stage',
              isBattleType: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/p-logo.png',
                  name: 'logo'
                }
              ],
              groups: {
                firstGroup: {
                  name: 'Group A',
                },
                secondGroup: {
                  name: 'Group B',
                },
                match: 'Match #2'
              },
              winner: 'Natus Vincere (A) - 233pts'
            },
            {
              id: generateId(),
              tournamentName: 'Group Stage',
              isBattleType: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/p-logo.png',
                  name: 'logo'
                }
              ],
              groups: {
                firstGroup: {
                  name: 'Group A',
                },
                secondGroup: {
                  name: 'Group B',
                },
                match: 'Match #2'
              },
              winner: 'Natus Vincere (A) - 233pts'
            },
            {
              id: generateId(),
              tournamentName: 'Group Stage',
              isBattleType: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/p-logo.png',
                  name: 'logo'
                }
              ],
              groups: {
                firstGroup: {
                  name: 'Group A',
                },
                secondGroup: {
                  name: 'Group B',
                },
                match: 'Match #2'
              },
              winner: 'Natus Vincere (A) - 233pts'
            },
            {
              id: generateId(),
              tournamentName: 'Group Stage',
              isBattleType: true,
              time: '19:00',
              date: '29 октября',
              logos: [
                {
                  id: generateId(),
                  src: '/img/p-logo.png',
                  name: 'logo'
                }
              ],
              groups: {
                firstGroup: {
                  name: 'Group A',
                },
                secondGroup: {
                  name: 'Group B',
                },
                match: 'Match #2'
              },
              winner: 'Natus Vincere (A) - 233pts'
            },
          ]
        },
      ]
    }
  },
  computed: {
    tabContent() {
      return this.tabs[this.activeIndex].content;
    }
  },
  methods: {
    changeTab(index) {
      this.activeIndex = index;
    }
  }
}
</script>

<style lang="sass">
@import '@/assets/sass/helpers/index'

.v-tabs
  z-index: 2
  position: relative
  margin-top: -60px
  +sm
    margin-top: -50px
  &__item
    padding: 60px 0
</style>
