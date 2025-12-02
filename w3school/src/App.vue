<template>
  <h1>Example</h1>
  <p>Click the button to fetch data with an HTTP request.</p>
  <p>Each click generates an object with a random user from <a href="https://randomuser.me/api/" target="_blank">https://randomuser.me/api/</a>.</p>
  <p>The robot avatars are lovingly delivered by <a href="http://Robohash.org" target="_blank">RoboHash</a>.</p>
  <button @click="fetchData">Fetch data</button>
  <div v-if="data" id="dataDiv">
    <img :src="data.picture.large" alt="avatar">
    <pre>{{ data.name.title + " " + data.name.first + " " + data.name.last }}</pre>
    <p>"{{ data.phone }}"</p>
  </div>
<!--  <pre v-if="data">{{ data }}</pre>-->
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      data: null,
    };
  },
  methods: {
    async fetchData() {
      const response = await axios.get("https://randomuser.me/api/");
      this.data = response.data.results[0];
    }
  }
};
</script>

<style>
#dataDiv {
  width: 240px;
  background-color: aquamarine;
  border: solid black 1px;
  margin-top: 10px;
  padding: 10px;
}
#dataDiv > img {
  width: 100%;
}
pre {
  font-size: larger;
  font-weight: bold;
}
</style>
