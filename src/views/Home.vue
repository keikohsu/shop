<template lang="pug">
  #home
    b-row
      b-col(cols="12" md="6" lg="3" v-for="(item, index) in items" :key="index")
        b-card(:title="item.name" :img-src="item.img" img-top :sub-title="'$'+item.price")
          b-button(variant="primary" @click="addCart(item)")
            font-awesome-icon(:icon="['fas', 'shopping-cart']")
            | &nbsp;加入購物車
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      items: [
        {
          img: 'https://c.ecimg.tw/items/DXAX28A900AT004/000002_1604455767.jpg',
          name: 'NIKE 白鞋',
          price: 1111
        },
        {
          img: 'https://c.ecimg.tw/items/DGBJDE1900AB40Y/000002_1604368410.jpg',
          name: 'Switch',
          price: 9580
        },
        {
          img: 'https://f.ecimg.tw/items/DHAG4SA900ASCRB/000002_1603524733.jpg',
          name: 'HP筆電',
          price: 19111
        },
        {
          img: 'https://b.ecimg.tw/items/DXAX2BA900AJR62/000002_1584518031.jpg',
          name: 'NIKE 米色鞋',
          price: 2911
        }
      ]
    }
  },
  methods: {
    addCart (item) {
      this.$store.commit('addCart', item)
    }
  }
}
</script>
