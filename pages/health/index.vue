<template>
  <TheNewsContent :category="'health'" />
</template>

<script>
const TheNewsContent = () => import('~/components/TheNewsContent')

export default {
  components: {
    TheNewsContent
  },

  head() {
    return {
      title: 'Health - KepoBro News',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Berita lengkap dan terupdate mengenai health dari News API'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'Health - KepoBro News'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Berita lengkap dan terupdate mengenai health dari News API'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Health - KepoBro News'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://news.andriannus.id/health'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Berita lengkap dan terupdate mengenai health dari News API'
        },
        {
          hid: 'twiter:title',
          name: 'twiter:title',
          content: 'Health - KepoBro News'
        }
      ]
    }
  }
}
</script>
