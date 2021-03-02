<template>
  <div class="flex justify-center pt-6">
    <div>
      <div class="text-center text-base font-black text-lg pb-6">
        Golden sponsor
      </div>
      <div class="rounded-full h-40 w-40">
        <a :href="sponsor.href">
          <img :src="sponsor.src" :title="sponsor.title" />
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    sponsor: {
      type: Object,
      required: true,
    },
  },
}
</script>
