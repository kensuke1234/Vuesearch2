
<template>

  <div class="search">

    <h2>星の名前は...</h2>
    <form v-on:submit.prevent="getResult(query)">
      <input type="text" placeholder="Search" v-model="query" />
    </form>
    <div class="results" v-if="results">
      <div v-for="result in results">
          <img v-bind:src="result.links[0].href" />
      </div>
    </div>
  </div>
  
</template>



<script>
import axios from 'axios';
export default {
  name: 'search',
  data () {
    return {
      msg: 'search',
      query: '',
      results: ''
    }
  },
  methods: {
      getResult(query) {
        axios.get('https://images-api.nasa.gov/search?q=' + query + '&media_type=image').then( response => {
            console.log(response.data.collection.items);
            this.results = response.data.collection.items;
        });
      }
  }
}
  </script>


<style>


body { 
  background: url('FullMoon2010.png')
  no-repeat;
  background-position: right;
  background-color: black;
  background-attachment: fixed;

  }
.results img {
    height: 300px;
    margin: 10px;
}
h1, h2 {
  font-weight: normal;
}


ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.moon {
  position: absolute;
  right: 0;
  top: 100px;
  width: 100px;
  z-index: 10;
}

@media screen and (max-width: 700px) {
  .moon {
    z-index: 0;
  }
}
</style>

