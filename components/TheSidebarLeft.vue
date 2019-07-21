<template>
  <div>
    <div
      class="card is-hidden-mobile sidebar"
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
              <router-link
                to="/business"
              >
                Business
              </router-link>
            </li>

            <li>
              <router-link
                to="/entertainment"
              >
                Entertainment
              </router-link>
            </li>

            <li>
              <router-link
                to="/health"
              >
                Health
              </router-link>
            </li>

            <li>
              <router-link
                to="/science"
              >
                Science
              </router-link>
            </li>

            <li>
              <router-link
                to="/sports"
              >
                Sports
              </router-link>
            </li>

            <li>
              <router-link
                to="/technology"
              >
                Technology
              </router-link>
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
            <router-link to="/business">
              <span class="icon is-small">
                <i class="fas fa-briefcase" aria-hidden="true" />
              </span>

              <span>Business</span>
            </router-link>
          </li>

          <li>
            <router-link to="/entertainment">
              <span class="icon is-small">
                <i class="fas fa-image" aria-hidden="true" />
              </span>

              <span>Entertainment</span>
            </router-link>
          </li>

          <li>
            <router-link to="/health">
              <span class="icon is-small">
                <i class="fas fa-heartbeat" aria-hidden="true" />
              </span>

              <span>Health</span>
            </router-link>
          </li>

          <li>
            <router-link to="/science">
              <span class="icon is-small">
                <i class="fas fa-atom" aria-hidden="true" />
              </span>

              <span>Science</span>
            </router-link>
          </li>

          <li>
            <router-link to="/sports">
              <span class="icon is-small">
                <i class="fas fa-dumbbell" aria-hidden="true" />
              </span>

              <span>Sports</span>
            </router-link>
          </li>

          <li>
            <router-link to="/technology">
              <span class="icon is-small">
                <i class="fas fa-mobile-alt" aria-hidden="true" />
              </span>

              <span>Technology</span>
            </router-link>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>
