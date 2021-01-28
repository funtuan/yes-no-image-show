<template>
  <div id="app">
    <div>
      12345
    </div>
    <div>
      <img :src="imageUrl" alt="">
    </div>
    <div>
      <button @click="changeImage">
        換圖片
      </button>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  data() {
    return {
      imageUrl: '',
    }
  },
  created() {
    this.changeImage()
  },
  methods: {
    async changeImage() {
      this.imageUrl = ''
      const res = await axios.get('https://yesno.wtf/api')
      this.imageUrl = res.data.image
    }
  }
}
</script>

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
