<template>
  <TheNewsContent :category="'science'" />
</template>

<script>
const TheNewsContent = () => import('~/components/TheNewsContent')

export default {
  components: {
    TheNewsContent
  },

  head() {
    return {
      title: 'Science - KepoBro News',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Berita lengkap dan terupdate mengenai science dari News API'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'Science - KepoBro News'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Berita lengkap dan terupdate mengenai science dari News API'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Science - KepoBro News'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://news.andriannus.id/science'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Berita lengkap dan terupdate mengenai science dari News API'
        },
        {
          hid: 'twiter:title',
          name: 'twiter:title',
          content: 'Science - KepoBro News'
        }
      ]
    }
  }
}
</script>
