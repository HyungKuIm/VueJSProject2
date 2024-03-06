<script>
//https://api.thecatapi.com/v1/images/search?limit=10
import {onMounted, ref} from "vue";

export  default {
  setup() {
    //const list = [{"id":"j","url":"https://24.media.tumblr.com/tumblr_krwvxh6KLK1qa9hjso1_1280.jpg","width":1002,"height":720},{"id":"29s","url":"https://cdn2.thecatapi.com/images/29s.jpg","width":500,"height":333},{"id":"7mi","url":"https://cdn2.thecatapi.com/images/7mi.jpg","width":496,"height":317},{"id":"b1a","url":"https://cdn2.thecatapi.com/images/b1a.jpg","width":550,"height":439},{"id":"bl8","url":"https://cdn2.thecatapi.com/images/bl8.jpg","width":400,"height":549},{"id":"cfp","url":"https://cdn2.thecatapi.com/images/cfp.jpg","width":3264,"height":1836},{"id":"d99","url":"https://cdn2.thecatapi.com/images/d99.jpg","width":2448,"height":3264},{"id":"edc","url":"https://cdn2.thecatapi.com/images/edc.jpg","width":640,"height":424},{"id":"o81wWm6-Z","url":"https://cdn2.thecatapi.com/images/o81wWm6-Z.jpg","width":3006,"height":2442},{"id":"V00qLe4Gw","url":"https://cdn2.thecatapi.com/images/V00qLe4Gw.jpg","width":1920,"height":1280}]
    const list = ref([])
    // onMounted(async () => {
    //   console.log("mounted")
    //   const data = await fetch('https://api.thecatapi.com/v1/images/search?limit=10')
    //   console.log(data)
    //   list.value = await data.json();
    //   console.log(this.list)
    // })
    return {
      list
    }
  },
  methods: {
    async getApi() {
      console.log("getApi")
      const data = await fetch('https://api.thecatapi.com/v1/images/search?limit=10')
      //console.log(data)
      this.list.value = await data.json();
      //console.log(this.list.value)
    }
  }


}
</script>

<template>
  <button type="button" @click="getApi">Show</button>
  <ul>
    <li v-for="cat in list"><img :src="cat.url" alt=""></li>

  </ul>
</template>

<style scoped>

</style>