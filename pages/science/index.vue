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
  },

  data() {
    return {
      articles: [],
      isLoading: true,
      title: 'Science'
    }
  },

  mounted() {
    this.getNews()
  },

  methods: {
    getNews() {
      this.isLoading = true

      this.$axios.$get(`${API.URL}?apiKey=${API.KEY}&country=${API.COUNTRY}&category=science`)
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

    readArticle(article) {
      localStorage.setItem('article', JSON.stringify(article))

      this.$router.push('/read')
    }
  }
}
</script>
