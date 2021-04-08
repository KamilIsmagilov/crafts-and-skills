<template>
  <div>
    <div class="title text-center text-6xl font-black py-24">
      <span class="text-orange-500">Crafts</span>
      <span class="text-orange-400">&</span>
      <span class="text-orange-500">Skills</span>
    </div>
    <div class="flex justify-between">
      <div class="bg-gray-300 w-2/4 h-100">
      </div>
      <div class="pl-6">
        <div class="text-base">
          Hi! My name is Kamil Ocean. This is my project and this is my mission:
        </div>
        <div class="text-lg font-black">
          I want to make the studying of all skills free and accessible for all
          people around the world
        </div>
        <JumbotronSponsorsGolden :sponsors="goldenSponsors" />
      </div>
    </div>
    <JumbotronSponsorsSilver :sponsors="silverSponsors" />
    <JumbotronSponsorsBronze :sponsors="bronzeSponsors" />
  </div>
</template>

<script>
import firebase from 'firebase'
import firebaseConfig from '../firebase.config'

import JumbotronSponsorsGolden from '~/components/JumbotronSponsorsGolden'
import JumbotronSponsorsSilver from '~/components/JumbotronSponsorsSilver'
import JumbotronSponsorsBronze from '~/components/JumbotronSponsorsBronze'

// Initialize Cloud Firestore through Firebase
if (!firebase.apps.length) {
  firebase.initializeApp(firebaseConfig)
}

const db = firebase.firestore()

export default {
  components: {
    JumbotronSponsorsGolden,
    JumbotronSponsorsSilver,
    JumbotronSponsorsBronze
  },
  data () {
    return {
      allSponsors: []
    }
  },
  computed: {
    goldenSponsors () {
      return this.filterSponsorsByType('golden')
    },
    silverSponsors () {
      return this.filterSponsorsByType('silver')
    },
    bronzeSponsors () {
      return this.filterSponsorsByType('bronze')
    }
  },
  created () {
    db.collection('sponsors')
      .where('isActive', '==', true)
      .get()
      .then((querySnapshot) => {
        this.allSponsors = querySnapshot.docs.map(doc => doc.data())
      })
  },
  methods: {
    filterSponsorsByType (type) {
      return this.allSponsors.filter(sponsor => sponsor.type === type)
    }
  }
}
</script>

<style scoped>
.title {
  font-family: 'Lora', serif;
}
</style>
