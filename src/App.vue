<template>
  <div id="app">
    <Header />
    <b-container class="bv-example-row">
      <b-row>
        <b-col sm="6" offset="3">
          <Base
          :currentCard ="cardsdatas[index]"
          />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Base from './components/Base.vue'

export default {
  name: 'App',
  components: {
    Header, 
    Base
  },
  data()
  {
    return {
      cardsdatas: [],
      index:0
    }
  },

  mounted: function () {
    fetch('https://opentdb.com/api.php?amount=10&type=multiple', {
      method: 'get'
    })
    .then((response) => 
    {
      return response.json()
    })
    .then((jsonData) => 
    {
      this.cardsdatas = jsonData.results//denne her henter reslutaterne ud fra api'en, det vil sgie når jeg skal rode med koden skal den del laves om
    })
  }
}
</script>
<!--https://opentdb.com/api.php?amount=10&type=multiple-->
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
