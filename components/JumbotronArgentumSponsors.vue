<template>
  <div class="flex justify-center pt-24">
    <div
      v-for="(sponsor, idx) in sponsors"
      :key="idx"
      class="rounded-full h-23 w-23 mx-5"
      :class="{ 'bg-gray-300': !sponsor.src.length }"
    >
      <div
        v-if="!sponsor.src"
        class="rounded-full object-cover h-24 w-24"
      ></div>
      <a v-else :href="sponsor.href">
        <img
          class="rounded-full object-cover h-24 w-24"
          :src="sponsor.src"
          :title="sponsor.alt"
        />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'JumbotronArgentumSponsors',
  props: {
    sponsors: {
      type: Array,
      required: true,
    },
  },
}
</script>
