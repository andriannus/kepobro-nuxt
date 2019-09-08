<template>
  <nav
    aria-label="main navigation"
    class="navbar is-fixed-top is-dark"
    role="navigation"
  >
    <div class="container">
      <div class="navbar-brand">
        <nuxt-link
          class="navbar-item"
          to="/"
        >
          <img
            src="images/logo.jpg"
            alt="KepoBro News"
          >
        </nuxt-link>
      </div>

      <div class="navbar-menu">
        <div class="navbar-end">
          <div class="navbar-item">
            <div class="buttons">
              <a
                href="https://github.com/andriannus/kepobro-nuxt"
                class="button is-light"
              >
                <span class="icon">
                  <i class="fab fa-github" />
                </span>
                <span>GitHub</span>
              </a>

              <a
                href="https://news-react.andriannus.id"
                class="button is-info"
              >
                <span class="icon">
                  <i class="fab fa-react" />
                </span>
                <span>React.js</span>
              </a>

              <a
                href="https://kepobro-news.herokuapp.com"
                class="button is-danger"
              >
                <span class="icon">
                  <i class="fab fa-angular" />
                </span>
                <span>Angular</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>
