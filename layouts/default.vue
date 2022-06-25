<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light sticky-top">
      <div class="container-fluid">
        <a class="navbar-brand" href="/"
          ><img src="https://aegyo.id/logo_aegyo_full.png" height="50px"
        /></a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNavAltMarkup"
          aria-controls="navbarNavAltMarkup"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
          <a class="btn btn-primary ms-4" href="/live"
            >live <i class="bx bx-play-circle"></i
          ></a>
          <div class="navbar-nav ms-auto">
            <nuxt-link class="nav-link ms-5" to="/kpop">K-POP</nuxt-link>
            <nuxt-link class="nav-link" to="/kdrama">K-DRAMA</nuxt-link>
            <nuxt-link class="nav-link" to="/kbeauty">K-BEAUTY</nuxt-link>
            <nuxt-link class="nav-link" to="/entertaiment"
              >ENTERTAIMENT</nuxt-link
            >
            <nuxt-link class="nav-link" to="/lifestyle">LIFESTYLE</nuxt-link>
            <nuxt-link class="nav-link" to="/movies">MOVIES</nuxt-link>
            <nuxt-link class="nav-link" to="/gallery">GALLERY</nuxt-link>
            <nuxt-link class="nav-link" to="/quiz">QUIZ</nuxt-link>
          </div>
          <form class="d-flex ms-3">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
            <button class="btn btn-outline-success" type="submit">
              Search
            </button>
          </form>
        </div>
      </div>
    </nav>
    <div class="">
      <nuxt />
    </div>
    <div class="footer">
      <p>
        Created with <i class="bi bi-suit-heart-fill text-danger"></i> by
        <a
          href="https://www.instagram.com/bianda880/"
          class="text-white fw-bold"
          >Bianda</a
        >
      </p>
    </div>
  </div>
</template>
