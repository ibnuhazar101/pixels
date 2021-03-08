<template>
  <div class="container-xxl nav-back">
    <nav class="navbar navbar-expand-lg navbar-light p-3">
      <div class="container-md">

        <div class="d-flex align-items-center flex-grow-0 bd-highlight">
          <a class="navbar-logo mr-5" href="/">Pixels</a>
          <form class="d-flex">
            <input class="form-control mr-1 search-key" type="search" placeholder="Search Photos..." aria-label="Search" style="width: 32rem; height: 50px;">
          </form>
        </div>

        <div class="bd-highlight">
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse float-right" id="navbarNavAltMarkup">
            <div class="navbar-nav">
              <a class="nav-link btn" href="/explore">Explore</a>
            </div>
          </div>
        </div>

      </div>
    </nav>
  </div>
</template>

<script>
export default {

}
</script>

<style>

.navbar {
  background-color: rgb(30, 136, 127);
  height: 65px;
  border-bottom: 2px solid black;
}

.navbar-logo {
  font-size: 1.7rem;
  font-weight: bold;
  color: rgb(204, 241, 38);
}

.navbar-logo:hover {
  text-decoration: none;
  color: rgb(204, 241, 38);
}

.search-key {
  box-shadow: none;
}

.btn-search {
  background-color: rgb(30, 136, 127);
  padding: 0 18px;
}

.navbar-nav a {
  color: rgb(204, 241, 38) !important;
  font-size: 1.2rem;
}

.navbar-nav a:hover {
  text-decoration: none;
  color: white !important;
}

</style>