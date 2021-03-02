<template>
  <div>
    <div class="title text-center text-6xl font-black py-24">
      <span class="text-orange-500">Crafts</span>
      <span class="text-orange-400">&</span>
      <span class="text-orange-500">Skills</span>
    </div>
    <div class="flex justify-between">
      <div>
        <iframe
          width="560"
          height="315"
          src="https://www.youtube.com/embed/H1cq99MGHbY"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
      <div class="pl-6">
        <div class="text-base">
          Hi! My name is Kamil Ocean. This is my project and this is my mission:
        </div>
        <div class="text-lg font-black">
          I want to make the studying of all skills free and accessible for all
          people around the world
        </div>
        <JumbotronGoldenSponsor v-if="goldenSponsor" :sponsor="goldenSponsor" />
      </div>
    </div>
    <JumbotronArgentumSponsors
      v-if="silverSponsors"
      :sponsors="silverSponsors"
    />
    <JumbotronBronzeSponsors v-if="bronzeSponsors" :sponsors="bronzeSponsors" />
  </div>
</template>

<script>
// const firebase = require("firebase")
import firebase from 'firebase'
import firebaseConfig from '../firebase.config'
import JumbotronGoldenSponsor from '~/components/JumbotronGoldenSponsor'
import JumbotronArgentumSponsors from '~/components/JumbotronArgentumSponsors'
import JumbotronBronzeSponsors from '~/components/JumbotronBronzeSponsors'

// Initialize Cloud Firestore through Firebase
firebase.initializeApp(firebaseConfig)

const db = firebase.firestore()

export default {
  components: {
    JumbotronGoldenSponsor,
    JumbotronArgentumSponsors,
    JumbotronBronzeSponsors,
  },
  created() {
    db.collection('sponsors')
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          console.log(`${doc.id} => ${JSON.stringify(doc.data())}`)
        })
      })
  },
}
</script>

<style scoped>
.title {
  font-family: 'Lora', serif;
}
</style>
