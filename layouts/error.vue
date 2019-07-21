<template>
  <div class="has-text-centered">
    <div v-if="error.statusCode === 404" class="mb-10">
      <img
        src="images/error-404.png"
        alt="Error 404 - Smashicons"
        width="40%"
      >
    </div>

    <nuxt-link
      class="button is-dark"
      to="/"
    >
      Back to Home
    </nuxt-link>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: null
    }
  },

  head() {
    return {
      title: 'Page Not Found - KepoBro News',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Halaman tidak ditemukan. Silahkan kembali ke halaman awal.'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'Page Not Found - KepoBro News'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Halaman tidak ditemukan. Silahkan kembali ke halaman awal.'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Page Not Found - KepoBro News'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://news.andriannus.id'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Halaman tidak ditemukan. Silahkan kembali ke halaman awal.'
        },
        {
          hid: 'twiter:title',
          name: 'twiter:title',
          content: 'Page Not Found - KepoBro News'
        }
      ]
    }
  }
}
</script>
