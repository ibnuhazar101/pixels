<template>
  <div class="">
    <Navbar />
    <div class="sub-topic">
      <div class="card-con row">
        <div v-for="(item, id) in arraySearch" :key="id">

        </div>
            <!-- <div class="card col-auto" id="kategory" value="nature">
              <ExploreCard 
                :photoCards="dataCards"
              />
              <div class="card-title">
                <h4>Donuts</h4>
                <h5>{{ totalPhoto }}</h5>
              </div>
            </div>
            <div class="card col-auto">
              <ExploreCard 
                :photoCards="dataCards"
              />
              <div class="card-title">
                <h4>Donuts</h4>
                <h5>{{ totalPhoto }}</h5>
              </div>
            </div>
            <div class="card col-auto">
              <ExploreCard 
                :photoCards="dataCards"
              />
              <div class="card-title">
                <h4>Donuts</h4>
                <h5>{{ totalPhoto }}</h5>
              </div>
            </div> -->
      </div>
    </div>



  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      apiKey: '563492ad6f9170000100000118525855ee1347bfb643086f67f0af4f',
      dataCards: [],
      totalPhoto: '',
      searchKey: 'work',
      arraySearch: ['nature', ]
    }
  },
  mounted() {
    // this.getDataCards()
  },
  methods: {
    async setDataResponse(value) {
          // const parentContainer = document.createElement('div')
          // const child = document.createElement('p')
          // child.innerHTML = value
          // parentContainer.appendChild(child)
          // console.log(parentContainer);
          // return parentContainer

      axios.get(`https://api.pexels.com/v1/search?query=${value}`, {
        headers: {
          Authorization: this.apiKey
        }
      })
      .then (res => {
        const responseData = res.data
        if (responseData) {
          const parentContainer = document.createElement('div')
          const child = document.createElement('p')
          child.innerHTML = responseData.total_results
          parentContainer.appendChild(child)
          console.log(parentContainer);
          return parentContainer
        }
      })
      .catch (err => {
        console.log(err);
      })
    },
    getDataCards(value) {
      axios.get(`https://api.pexels.com/v1/search?query=${value}`, {
        headers: {
          Authorization: this.apiKey
        }
      })
      .then (res => {
        // this.responseData = res.data.photos
        return res.data
        //  this.responseData = res.data
        // this.totalPhoto = res.data.total_results
      })
      .catch (err => {
        console.log(err);
      })
    }
  }
}
</script>

<style>

.sub-topic {
  display: flex;
  justify-content: center;
  margin: 3rem auto;
  width: 100%;
}

.card-con {
  width: 85%;
  display: flex;
  justify-content: space-between;
}

.card {
  padding: 0.5rem;
  border: none;
  border-radius: 15px;
  transition: 0.3s;
  cursor: pointer;
}

.card-title {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0 5px;
  margin-bottom: -5px;
}

.card:hover {
  background-color: rgb(230, 227, 227);
}

</style>