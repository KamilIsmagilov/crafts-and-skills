<template>
  <div>
    <div class="text-center text-base font-black text-lg pb-6 pt-24">
      Bronze sponsors:
    </div>
    <div class="flex justify-center">
      <div
        v-for="(sponsor, idx) in sponsors"
        :key="idx"
        class="rounded-full h-16 w-16 mx-5"
      >
        <a :href="sponsor.href">
          <img
            class="rounded-full object-cover h-16 w-16"
            :src="sponsor.src"
            :title="sponsor.title"
          />
        </a>
      </div>
      <div
        v-for="idx in restSponsors"
        :key="idx"
        class="rounded-full h-16 w-16 mx-5 bg-gray-300"
      />
    </div>
  </div>
</template>

<script>
import JumbotronSponsors from '~/mixins/JumbotronSponsors'

export default {
  name: 'JumbotronSponsorsBronze',
  mixins: [JumbotronSponsors],
  computed: {
    restSponsors () {
      return 10 - this.sponsors?.length
    }
  }
}
</script>
