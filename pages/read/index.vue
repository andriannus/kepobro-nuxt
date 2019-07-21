<template>
  <div>
    <div
      v-if="isNotFound === false"
      class="card"
    >
      <header class="card-header">
        <span class="card-header-title">
          <a
            class="mr-10"
            @click="back()"
          >
            <span class="icon is-small">
              <i class="fas fa-arrow-left" />
            </span>
          </a>

          <span>Read</span>
        </span>
      </header>

      <div class="card-content has-text-justified">
        <figure class="image mb-10">
          <img
            :src="article.urlToImage"
            :alt="article.title"
            onerror="this.src='https://bulma.io/images/placeholders/480x320.png'"
          >
        </figure>

        <h1 class="title is-size-5 mb-10">
          {{ article.title }}
        </h1>

        <div class="level">
          <div class="level-left">
            <span class="is-size-7">
              {{ article.author }}
            </span>
          </div>

          <div class="level-right">
            <span class="is-size-7">
              {{ article.publishedAt | dateID }}
            </span>
          </div>
        </div>

        <p class="is-size-6">
          {{ article.content | article }}
        </p>
      </div>

      <footer class="card-footer">
        <a
          :href="article.url"
          class="card-footer-item"
          rel="noreferrer"
          target="blank"
        >
          <span>Continue Reading</span>

          <span class="icon">
            <i class="fas fa-external-link-square-alt" />
          </span>
        </a>
      </footer>
    </div>

    <div
      v-if="isNotFound === true"
      class="has-text-centered"
    >
      <div class="mb-10">
        <img
          src="assets/images/not-found.png"
          alt="Not Found - Freepik"
          width="40%"
        >
      </div>

      <p class="is-size-5 mb-10">
        <em>No article selected</em>
      </p>

      <nuxt-link
        class="button is-dark"
      >
        Back to Home
      </nuxt-link>
    </div>
  </div>
</template>

<script>
import { format } from 'date-fns'
import idLocale from 'date-fns/locale/id'

export default {
  filters: {
    article: (text) => {
      if (!text) return ''

      const tempArr = text.split('')
      const startSub = tempArr.indexOf('[')
      const finishSub = tempArr.indexOf(']')
      const substractSub = Number(finishSub) - Number(startSub) + 1
      const findString = text.substr(startSub, substractSub)

      return text.replace(findString, '')
    },

    dateID: (date) => {
      if (!date) return ''

      return format(date, 'dddd, DD MMMM YYYY · HH:mm', { locale: idLocale })
    }
  },

  head() {
    return {
      title: 'Reading News - KepoBro News',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Baca berita terpilih dari News API'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'Reading News - KepoBro News'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Baca berita terpilih dari News API'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Reading News - KepoBro News'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://news.andriannus.id/Reading News'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Baca berita terpilih dari News API'
        },
        {
          hid: 'twiter:title',
          name: 'twiter:title',
          content: 'Reading News - KepoBro News'
        }
      ]
    }
  },

  data() {
    return {
      article: {},
      isNotFound: false
    }
  },

  mounted() {
    this.getArticle()
  },

  methods: {
    getArticle() {
      const data = localStorage.getItem('article') || ''

      if (!!data === true) {
        this.isNotFound = false

        this.article = JSON.parse(data)
      } else {
        this.isNotFound = true
      }
    },

    back() {
      localStorage.removeItem('article')

      this.$router.go(-1)
    }
  }
}
</script>
