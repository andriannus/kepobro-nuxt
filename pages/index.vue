<template>
  <TheNewsContent :category="'trending'" />
</template>

<script>
const TheNewsContent = () => import('~/components/TheNewsContent')

export default {
  components: {
    TheNewsContent
  },

  head() {
    return {
      title: 'KepoBro News - Kepoin tentang yang hits saat ini!',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Berita lengkap dan terupdate dari News API'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'KepoBro News - Kepoin tentang yang hits saat ini!'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Berita lengkap dan terupdate dari News API'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'KepoBro News - Kepoin tentang yang hits saat ini!'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://news.andriannus.id'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Berita lengkap dan terupdate dari News API'
        },
        {
          hid: 'twiter:title',
          name: 'twiter:title',
          content: 'KepoBro News - Kepoin tentang yang hits saat ini!'
        }
      ]
    }
  }
}
</script>
