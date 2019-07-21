<template>
  <div class="card">
    <header class="card-header">
      <span class="card-header-title">
        Business
      </span>

      <a
        v-if="isLoading === false"
        class="card-header-icon"
        title="Refresh News"
        @click="getNews()"
      >
        <span class="icon">
          <i class="fas fa-sync-alt" />
        </span>
      </a>
    </header>

    <div class="card-content">
      <progress
        v-if="isLoading === true"
        class="progress is-small is-dark"
        max="100"
      >
        15%
      </progress>

      <div v-if="isLoading === false">
        <article
          v-for="(article, index) in articles"
          :key="index"
          class="media"
        >
          <figure class="media-left mt-5">
            <p class="image is-64x64">
              <img
                v-if="!!article.urlToImage === true"
                :src="article.urlToImage"
                onerror="this.src='https://bulma.io/images/placeholders/480x320.png'"
              >

              <img
                v-if="!!article.urlToImage === false"
                src="https://bulma.io/images/placeholders/480x320.png"
              >
            </p>
          </figure>

          <div class="media-content">
            <div
              class="content"
            >
              <p class="has-text-justified mb-10">
                <a @click="readArticle(article)">
                  <strong>{{ article.title }}</strong>
                </a>
              </p>
              <span>
                <i class="fas fa-globe mr-5" />

                {{ article.source.name }}
              </span>
            </div>
          </div>
        </article>
      </div>
    </div>

    <footer
      v-if="isLoading === false"
      class="card-footer"
    >
      <div class="card-footer-item">
        <span>
          <em>All displayed</em>
        </span>
      </div>
    </footer>
  </div>
</template>

<script>
import { API } from '~/assets/consts/api'

export default {
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
      isLoading: false
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
    },

    readArticle(article) {
      localStorage.setItem('article', JSON.stringify(article))

      this.$router.push('/read')
    }
  }
}
</script>
