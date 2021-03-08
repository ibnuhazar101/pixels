<template>
  <div class="back d-flex justify-content-center">

    <div class="carousel">
      <img src="~/assets/images/jumbotron/jumbo1.jpg" class="d-block w-100" alt="...">
    </div>

    <div class="main-text align-self-center d-flex justify-content-center">
      <h1>
        The best free stock photos <br>
        shared by talented creators.
      </h1>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

.back {
  position: relative;
}

.carousel img {
  height: 450px;
  object-fit: cover;
  border-radius: 0 0 30px 30px;
}

.main-text {
  position: absolute;
  bottom: 40%;
  color: white;
  font-size: 2rem;
}

</style>