<template>
  <TheNewsContent :category="'entertainment'" />
</template>

<script>
const TheNewsContent = () => import('~/components/TheNewsContent')

export default {
  components: {
    TheNewsContent
  },

  head() {
    return {
      title: 'Entertainment - KepoBro News',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Berita lengkap dan terupdate mengenai entertainment dari News API'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'Entertainment - KepoBro News'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Berita lengkap dan terupdate mengenai entertainment dari News API'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Entertainment - KepoBro News'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://news.andriannus.id/entertainment'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Berita lengkap dan terupdate mengenai entertainment dari News API'
        },
        {
          hid: 'twiter:title',
          name: 'twiter:title',
          content: 'Entertainment - KepoBro News'
        }
      ]
    }
  }
}
</script>
