<template>
  <section class="section">
    <TheNavbar />

    <div class="container">
      <div class="columns">
        <div class="column">
          <TheSidebarLeft />
        </div>

        <div class="column is-half">
          <nuxt />
        </div>

        <div class="column">
          <TheSidebarRight />
        </div>
      </div>
    </div>

    <button
      id="btnBackToTop"
      class="button is-dark is-medium"
      @click="backToTop()"
    >
      <span class="icon">
        <i class="fas fa-angle-double-up" />
      </span>
    </button>
  </section>
</template>

<style lang="scss" scoped>
#btnBackToTop {
  display: none;
  position: fixed;
  bottom: 30px;
  right: 30px;
}
</style>

<script>
const TheNavbar = () => import('~/components/TheNavbar')
const TheSidebarLeft = () => import('~/components/TheSidebarLeft')
const TheSidebarRight = () => import('~/components/TheSidebarRight')

export default {
  components: {
    TheNavbar,
    TheSidebarLeft,
    TheSidebarRight
  },

  mounted() {
    window.onscroll = () => {
      const button = document.getElementById('btnBackToTop')

      if (document.body.scrollTop > 300 || document.documentElement.scrollTop > 300) {
        button.style.display = 'block'
      } else {
        button.style.display = 'none'
      }
    }
  },

  methods: {
    backToTop() {
      document.body.scrollTop = 0
      document.documentElement.scrollTop = 0
    }
  }
}
</script>
