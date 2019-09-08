<template>
  <TheNewsContent :category="'sports'" />
</template>

<script>
const TheNewsContent = () => import('~/components/TheNewsContent')

export default {
  components: {
    TheNewsContent
  },

  head() {
    return {
      title: 'Sports - KepoBro News',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Berita lengkap dan terupdate mengenai sports dari News API'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'Sports - KepoBro News'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Berita lengkap dan terupdate mengenai sports dari News API'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Sports - KepoBro News'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://news.andriannus.id/sports'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Berita lengkap dan terupdate mengenai sports dari News API'
        },
        {
          hid: 'twiter:title',
          name: 'twiter:title',
          content: 'Sports - KepoBro News'
        }
      ]
    }
  }
}
</script>
