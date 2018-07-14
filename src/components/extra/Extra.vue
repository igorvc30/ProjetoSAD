<template>
  <div class="extra">
    <vuestic-widget :headerText="'extra.tabs.title' | translate" class="no-v-padding">
      <vuestic-tabs class="tabs" :names="[$t('extra.tabs.setupProfile'), $t('extra.tabs.overview')]">
        <div :slot="'extra.tabs.overview' | translate" class="d-flex justify-content-center">
          <overview-tab></overview-tab>
        </div>
        <div :slot="'extra.tabs.setupProfile' | translate" class="d-flex justify-content-center">
          <setup-profile-tab wizardType="simple"></setup-profile-tab>
        </div>
      </vuestic-tabs>
    </vuestic-widget>

    <div class="row">
      <div v-for="item in contatos" :key="item.id" class="col-md-3 d-flex">
        <vuestic-widget :headerText="$t('extra.profileCard')" class="profile-card-widget">
          <vuestic-profile-card :name="item.nome" :location="item.curso" photoSource="item.foto"
                                :social="{twitter: 'twitter.com', facebook: 'facebook.com',
                                  instagram: 'instagram.com'}">
          </vuestic-profile-card>
        </vuestic-widget>
      </div>
    </div>
  </div>
</template>

<script>
  import OverviewTab from 'components/dashboard/features-tab/FeaturesTab.vue'
  import SetupProfileTab from 'components/dashboard/setup-profile-tab/SetupProfileTab.vue'
  import LeafletMap from 'components/maps/leaflet-maps/LeafletMap.vue'

  export default {
    name: 'extra',
    components: {
      LeafletMap,
      SetupProfileTab,
      OverviewTab
    },
    data () {
      return {
        chatMessages: [
          {
            text: 'Hello! So glad you liked my work. Do you want me to shoot you?',
            yours: false
          },
          {
            text: 'Yeah, that would be cool. Maybe this Sunday at 3 pm?',
            yours: true
          },
          {
            text: 'Sounds great! See you later!',
            yours: false
          },
          {
            text: 'Should I bring a lightbox with me?',
            yours: true
          },
          {
            text: 'No, thanks. There is no need. Can we set up a meeting earlier?',
            yours: false
          },
          {
            text: 'I\'m working on Vuestic, so let\'s meet at 3pm. Thanks!',
            yours: true
          }
        ],
        posts: [
          {
            name: 'Irina Myatelskaya',
            text: 'joined the network',
            photoURL: 'http://i.imgur.com/VuTDC8u.png'
          },
          {
            name: 'Andrei Hrabouski',
            text: 'has just started a live video',
            photoURL: 'http://i.imgur.com/W3mGrmW.png'
          },
          {
            name: 'Evan You',
            text: 'joined the network',
            photoURL: 'http://i.imgur.com/D7DOGBH.jpg'
          }
        ],
        news: [
          {
            photoURL: 'http://i.imgur.com/PiTDDcA.png'
          },
          {
            photoURL: 'http://i.imgur.com/M6GugaM.png'
          },
          {
            photoURL: 'http://i.imgur.com/vEy3fRU.png'
          },
          {
            photoURL: 'http://i.imgur.com/Xrywphx.png'
          },
          {
            photoURL: 'http://i.imgur.com/dqVtQGY.png'
          },
          {
            photoURL: 'http://i.imgur.com/qP7rTCy.png'
          },
          {
            photoURL: 'http://i.imgur.com/6YLsM43.png'
          },
          {
            photoURL: 'http://i.imgur.com/9PAOx55.png'
          },
          {
            photoURL: 'http://i.imgur.com/mVpc04D.png'
          },
          {
            photoURL: 'http://i.imgur.com/WdbTSLn.png'
          },
          {
            photoURL: 'http://i.imgur.com/ZXRIHfk.png'
          }
        ],
        contatos: [
          {
            id: 1,
            nome: 'Igor V. Costa',
            curso: 'Sistemas de Informacao',
            linkedin: 'urlDOIDA',
            email: 'igor.vc30@gmail.com',
            foto: 'https://media.licdn.com/dms/image/C4E03AQE7RL2CI02FBg/profile-displayphoto-shrink_200_200/0?e=1536796800&v=beta&t=5WgNUK0czItXCld3f_zH3DXw_ZNh_EgBla6Cw4q_5yo'
          },
          {
            id: 2,
            nome: 'Igor V. Costa',
            curso: 'Sistemas de Informacao',
            linkedin: 'urlDOIDA',
            email: 'igor.vc30@gmail.com'
          }
        ]

      }
    }
  }
</script>

<style lang="scss" scoped>
  .tabs {
    .overview-tab {
      .explore-row {
        display: none !important;
      }
    }

    .maps-tab {
      height: 500px;
    }
  }

  .profile-card-widget, .chat-widget {
    width: 100%;
    .widget-body {
      display: flex;
      justify-content: center;
      align-items: center;
      & > div {
        width: 100%;
      }
    }
  }

  .bottom-widgets {
    > div[class^='col'] {
      & > div {
        width: 100%;
      }
    }
  }
</style>
