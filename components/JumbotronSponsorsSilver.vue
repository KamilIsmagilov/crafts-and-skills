<template>
  <div>
    <div class="text-center text-base font-black text-lg pb-6 pt-24">
      Silver sponsors:
    </div>
    <div class="flex justify-center">
      <div
        v-for="(sponsor, idx) in sponsors"
        :key="idx"
        class="rounded-full h-23 w-23 mx-5"
      >
        <a :href="sponsor.href">
          <img
            class="rounded-full object-cover h-24 w-24"
            :src="sponsor.src"
            :title="sponsor.title"
          />
        </a>
      </div>
      <div
        v-for="idx in restSponsors"
        :key="idx"
        class="rounded-full h-24 w-24 mx-5 bg-gray-300"
      ></div>
    </div>
  </div>
</template>

<script>
import JumbotronSponsors from '~/mixins/JumbotronSponsors'

export default {
  name: 'JumbotronSponsorsSilver',
  mixins: [JumbotronSponsors],
  computed: {
    restSponsors () {
      return 5 - this.sponsors?.length
    }
  }
}
</script>
