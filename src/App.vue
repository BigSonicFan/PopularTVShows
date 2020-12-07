<!--template for App.vue-->
<template>
  <div id="app">
    <!--where info from Header.vue will display-->
    <Header theTitle="Popular TV Shows"/>
    <br>
    <div class="row" style="margin-left:auto; margin-right:auto; text-align:center; display:inline-block;">
      <!--where info from CardList.vue will display-->
      <CardList v-bind:tvShowList="shows" class="row" style="padding-left:0px; padding-right:0px; text-align:center;" />
    </div>
  </div>
</template>

<script>
  //importing the vue files, bootstrap, and axios
  import Header from './components/Header.vue'
  import CardList from './components/CardList.vue'
  import 'bootstrap'
  import 'bootstrap/dist/css/bootstrap.min.css'
  import axios from 'axios'
  //exporting name, and components for App.vue
  export default {
    name: 'App',
    components: {
    Header,
    CardList
  },
  //data code
  data()
    {
    return {
      //what data returns
      shows: 0
    }
  },
  //mounted code
  mounted()
  {
    //axios getting the moviedb link for popular tv shows
    axios.get('https://api.themoviedb.org/3/tv/popular?api_key=0b6c8af4b6a78e76afe770ba13928edf')
    //the .then response
    .then ( (response) => {
      //setting the return data "shows" to only 4 response.data.results
      //slice method to only display 4
      this.shows = response.data.results.slice(0,4)

    })
  }
}
</script>

<!--style for id app-->
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
