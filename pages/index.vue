<template>
  <div>
    <div class="nav-top">
      <Navbar />
    </div>
    <Jumbotron />
    <div class="space" id="content"></div>
    <div class="mt-3 mb-3">
      <div class="row d-flex justify-content-center">
        <div class="col-9">
          <div class="photo d-block">
            <div v-for="(photo, id) in dataPhotos" :key="id" class="photo-list">
              <img :src="`${photo.src.medium}`" alt="">
            </div>
          </div>
        </div>
      </div>
      <div class="row d-flex justify-content-center">
        <div class="col-9 d-flex justify-content-between">
          <button class="btn-more" @click="getPrevPhotos()">
            Prev
          </button>
          <button class="btn-more" @click="getNextPhotos()">
            Next
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      apiKey: '563492ad6f917000010000013b5cb441b61348778dd8fc2f6665bc7f',
      dataPhotos: [],
      page: 1
    }
  },
  watch: {
    page() {
      this.getDataPhotos()
    }
  },
  mounted() {
    this.getDataPhotos()
  },
  methods: {
    getDataPhotos() {
      axios.get(`https://api.pexels.com/v1/curated?per_page=50&page=${this.page}`, {
        headers: {
          Authorization: this.apiKey
        }
      })
      .then (res => {
        this.dataPhotos = res.data.photos 
      })
      .catch (err => {
        console.log(err);
      })
    },
    getNextPhotos() {
      this.page += 1
      var elmnt = document.getElementById("content");
      elmnt.scrollIntoView(true);
    },
    getPrevPhotos() {
      this.page -= 1
      var elmnt = document.getElementById("content");
      elmnt.scrollIntoView(true);
    }
  }
}
</script>

<style>

.nav-top {
  position: sticky;
  top: 0;
  z-index: 1;
}

.space {
  margin: -63px;
  width: 100px;
  height: 132px;
}

.photo {
  width: 100%;
  column-count: 4;
  z-index: -1;
}

.photo-list {
  width: 17rem;
  margin-bottom: 1rem;
  cursor: pointer;
  z-index: -1;
}

.photo img {
  width: 100%;
  border-radius: 10px;
}

.btn-more {
  background-color: rgb(30, 136, 127);
  color: white;
  display: flex;
  border: none;
  padding: 6px 30px;
  margin: 15px;
  border-radius: 5px;
}

</style>
