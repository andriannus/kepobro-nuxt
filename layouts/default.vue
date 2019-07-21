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
  </section>
</template>

<script>
const TheNavbar = () => import('~/components/TheNavbar')
const TheSidebarLeft = () => import('~/components/TheSidebarLeft')
const TheSidebarRight = () => import('~/components/TheSidebarRight')

export default {
  components: {
    TheNavbar,
    TheSidebarLeft,
    TheSidebarRight
  }
}
</script>
