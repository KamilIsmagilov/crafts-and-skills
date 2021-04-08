<template>
  <div class="flex justify-center pt-6">
    <div>
      <div class="text-center text-base font-black text-lg pb-6">
        Golden sponsor
      </div>
      <div v-if="sponsor" class="rounded-full h-40 w-40">
        <a :href="sponsor.href" target="_blank">
          <img :src="sponsor.src" :title="sponsor.title" >
        </a>
      </div>
      <div v-else class="rounded-full h-40 w-40 mx-5 bg-gray-300" />
    </div>
  </div>
</template>

<script>
import JumbotronSponsors from '~/mixins/JumbotronSponsors'

export default {
  name: 'JumbotronSponsorsGolden',
  mixins: [JumbotronSponsors],
  computed: {
    sponsor() {
      return this.sponsors[0]
    }
  }
}
</script>
