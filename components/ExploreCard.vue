<template>
  <div class="container-fluid">
    <div class="outer-box">
      <div class="row">
        <div class="col-12 top-con">
          <div v-for="(photo, idTop) in photoCards.slice(0, 1)" :key="idTop" class="top-card">
              <img :src="`${photo.src.large}`" alt="">
          </div>
        </div>
      </div>
      <div class="row d-flex justify-content-center bottom-con">
        <div class="col-12 d-flex justify-content-between bottom-card">
          <div v-for="(photo, idBottom) in photoCards.slice(1, 5)" :key="idBottom" class="card-list">
            <img :src="`${photo.src.medium}`" alt="">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    photoCards: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style>

.outer-box {
  width: 350px;
}

.top-con {
  padding: 0;
}

.top-card img {
  width: 100%;
  height: 250px;
  object-fit: cover;
  border-radius: 10px;
}

.bottom-card {
  margin: 3px;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  overflow: hidden;
  border-radius: 10px;
}

.card-list {
  margin: 0;
  width: 5.85rem;
}
.card-list img {
  width: 100%;
  margin: 0;
  height: 65px;
  object-fit: cover;
}

</style>