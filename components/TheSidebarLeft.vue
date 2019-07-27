<template>
  <div class="sidebar">
    <div
      class="card is-hidden-mobile"
    >
      <header class="card-header">
        <span class="card-header-title">
          Categories
        </span>
      </header>

      <div class="card-content">
        <aside class="menu">
          <ul class="menu-list">
            <li>
              <nuxt-link
                to="/business"
              >
                Business
              </nuxt-link>
            </li>

            <li>
              <nuxt-link
                to="/entertainment"
              >
                Entertainment
              </nuxt-link>
            </li>

            <li>
              <nuxt-link
                to="/health"
              >
                Health
              </nuxt-link>
            </li>

            <li>
              <nuxt-link
                to="/science"
              >
                Science
              </nuxt-link>
            </li>

            <li>
              <nuxt-link
                to="/sports"
              >
                Sports
              </nuxt-link>
            </li>

            <li>
              <nuxt-link
                to="/technology"
              >
                Technology
              </nuxt-link>
            </li>
          </ul>
        </aside>
      </div>
    </div>

    <div class="bra-3 has-background-white">
      <div
        class="tabs is-toggle is-hidden-tablet"
      >
        <ul>
          <li>
            <nuxt-link to="/business">
              <span class="icon is-small">
                <i class="fas fa-briefcase" aria-hidden="true" />
              </span>

              <span>Business</span>
            </nuxt-link>
          </li>

          <li>
            <nuxt-link to="/entertainment">
              <span class="icon is-small">
                <i class="fas fa-image" aria-hidden="true" />
              </span>

              <span>Entertainment</span>
            </nuxt-link>
          </li>

          <li>
            <nuxt-link to="/health">
              <span class="icon is-small">
                <i class="fas fa-heartbeat" aria-hidden="true" />
              </span>

              <span>Health</span>
            </nuxt-link>
          </li>

          <li>
            <nuxt-link to="/science">
              <span class="icon is-small">
                <i class="fas fa-atom" aria-hidden="true" />
              </span>

              <span>Science</span>
            </nuxt-link>
          </li>

          <li>
            <nuxt-link to="/sports">
              <span class="icon is-small">
                <i class="fas fa-dumbbell" aria-hidden="true" />
              </span>

              <span>Sports</span>
            </nuxt-link>
          </li>

          <li>
            <nuxt-link to="/technology">
              <span class="icon is-small">
                <i class="fas fa-mobile-alt" aria-hidden="true" />
              </span>

              <span>Technology</span>
            </nuxt-link>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>
