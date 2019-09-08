<template>
  <TheNewsContent :category="'business'" />
</template>

<script>
const TheNewsContent = () => import('~/components/TheNewsContent')

export default {
  components: {
    TheNewsContent
  },

  head() {
    return {
      title: 'Business - KepoBro News',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Berita lengkap dan terupdate mengenai business dari News API'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'Business - KepoBro News'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Berita lengkap dan terupdate mengenai business dari News API'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Business - KepoBro News'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://news.andriannus.id/business'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Berita lengkap dan terupdate mengenai business dari News API'
        },
        {
          hid: 'twiter:title',
          name: 'twiter:title',
          content: 'Business - KepoBro News'
        }
      ]
    }
  }
}
</script>
