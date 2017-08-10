<template lang="html">
  <div class="columns is-mobile is-multiline is-centered">
    <div class="column is-one-third-desktop" v-for="p in products">
      <small-product :product="p" />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import SmallProduct from '~/components/SmallProduct.vue'

export default {
  components: {SmallProduct},
  async asyncData ({env, params}) {
    let {data} = await axios.get(`${env.cockpit.apiUrl}/collections/get/Product?token=${env.cockpit.apiToken}`)

    let products = await Promise.all(await data.map(async (p) => {
      let result = await axios.post(`${env.cockpit.apiUrl}/mediamanager/thumbnails?token=${env.cockpit.apiToken}`, {
        images: [p.Image],
        w: 300,
        h: 300,
        options: {
          quality: 80,
          mode: 'resize'
        }
      })

      p.ThumbUrl = `${env.cockpit.baseUrl}${result.data[p.Image]}`
      return p
    }))

    return {
      products
    }
  }
}
</script>
