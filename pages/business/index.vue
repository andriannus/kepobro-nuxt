<template>
  <TheNewsContent
    :articles="articles"
    :is-loading="isLoading"
    :title="title"
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
  },

  data() {
    return {
      articles: [],
      isLoading: true,
      title: 'Business'
    }
  },

  mounted() {
    this.getNews()
  },

  methods: {
    getNews() {
      this.isLoading = true

      this.$axios.$get(`${API.URL}?apiKey=${API.KEY}&country=${API.COUNTRY}&category=business`)
        .then((res) => {
          this.articles = res.articles
        })
        .catch(() => {
          this.articles = []
        })
        .finally(() => {
          this.isLoading = false
        })
    }
  }
}
</script>
