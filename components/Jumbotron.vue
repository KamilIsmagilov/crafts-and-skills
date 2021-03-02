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
        <JumbotronGoldenSponsor :sponsor="goldenSponsor" />
      </div>
    </div>
    <JumbotronArgentumSponsors :sponsors="argentumSponsors" />
    <JumbotronBronzeSponsors :sponsors="bronzeSponsors" />
  </div>
</template>

<script>
import JumbotronGoldenSponsor from '~/components/JumbotronGoldenSponsor'
import JumbotronArgentumSponsors from '~/components/JumbotronArgentumSponsors'
import JumbotronBronzeSponsors from '~/components/JumbotronBronzeSponsors'

export default {
  components: {
    JumbotronGoldenSponsor,
    JumbotronArgentumSponsors,
    JumbotronBronzeSponsors,
  },
  data() {
    return {
      goldenSponsor: {
        href: '',
        src:
          'https://sun9-52.userapi.com/impf/c846418/v846418296/b3b93/w_o3hfeUVOg.jpg?size=500x500&quality=96&sign=7842e7506e1c185dc0a43a0ee8850cc0&type=album',
        title: '',
      },
      argentumSponsors: [
        {
          href: 'https://vk.com/3dparrot',
          src:
            'https://sun9-29.userapi.com/impf/c850236/v850236161/1a24f3/sbzfnZrU-Ww.jpg?size=822x720&quality=96&sign=7aa343a6da0ff53972d837c4558d51b8&type=album',
          title: '3DParrot | Modeling & Sculpting',
        },
        {
          href: '',
          src:
            'https://cdn2.vectorstock.com/i/thumb-large/02/36/moscow-saint-basil-cathedral-vector-21060236.jpg',
          title: '',
        },
        {
          href: '',
          src:
            'https://cdn.shopify.com/shopifycloud/hatchful-web/assets/6fcc76cfd1c59f44d43a485167fb3139.png',
          title: '',
        },
        {
          href: '',
          src: '',
          title: '',
        },
        {
          href: '',
          src: '',
          title: '',
        },
      ],
      bronzeSponsors: [
        {
          href: '',
          src:
            'https://previews.123rf.com/images/saiful007/saiful0071708/saiful007170800392/83310472-decoration-flower-logo-design-concept-template.jpg',
          title: '',
        },
        {
          href: '',
          src:
            'https://techcrunch.com/wp-content/uploads/2018/07/logo-2.png?w=300',
          title: '',
        },
        {
          href: '',
          src:
            'https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/Telegram_logo.svg/1024px-Telegram_logo.svg.png',
          title: '',
        },
        {
          href: '',
          src:
            'https://www.freelogodesign.org/Content/img/logo-samples/bakary.png',
          title: '',
        },
        {
          href: '',
          src:
            'https://thumbs.dreamstime.com/b/logo-design-elegant-style-any-business-152363515.jpg',
          title: '',
        },
        {
          href: '',
          src: 'https://i.dlpng.com/static/png/6423218_preview.png',
          title: '',
        },
        {
          href: '',
          src:
            'https://www.designhill.com/resize_img.php?atyp=page_file&pth=ft_ca_ct||259||contestfile_2&flp=1549629083-6925880135c5d769b54cdd1-05446372.jpg',
          title: '',
        },
        {
          href: '',
          src:
            'https://www.logomaker.com/wp-content/uploads/2015/05/logo-maker-47.jpg',
          title: '',
        },
        {
          href: '',
          src: 'https://www.designmantic.com/images/travel-banner-image-1.png',
          title: '',
        },
        {
          href: '',
          src: '',
          title: '',
        },
      ],
    }
  },
}
</script>

<style scoped>
.title {
  font-family: 'Lora', serif;
}
</style>
