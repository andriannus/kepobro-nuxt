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
  },

  data() {
    return {
      articles: [],
      isLoading: true,
      title: 'Entertainment'
    }
  },

  mounted() {
    this.fetchNews()
  },

  methods: {
    fetchNews() {
      this.isLoading = true

      this.$axios.$get(`${API.URL}?apiKey=${API.KEY}&country=${API.COUNTRY}&category=entertainment`)
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
