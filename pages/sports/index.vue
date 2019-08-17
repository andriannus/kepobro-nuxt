<template>
  <TheNewsContent
    :articles="articles"
    :is-loading="isLoading"
    :title="title"
    @refetchNews="onRefetchNews"
  />
</template>

<script>
import { API } from '~/assets/consts/api'

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
  },

  data() {
    return {
      articles: [],
      isLoading: true,
      title: 'Sports'
    }
  },

  mounted() {
    this.fetchNews()
  },

  methods: {
    fetchNews() {
      this.isLoading = true

      this.$axios.$get(`${API.URL}?apiKey=${API.KEY}&country=${API.COUNTRY}&category=sports`)
        .then((res) => {
          this.articles = res.articles
        })
        .catch(() => {
          this.articles = []
        })
        .finally(() => {
          this.isLoading = false
        })
    },

    onRefetchNews() {
      this.fetchNews()
    }
  }
}
</script>
