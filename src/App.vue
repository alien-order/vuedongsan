<template>
  <div class="menu">
    <a href="" v-for="(a, i) in 메뉴들" :key="i">{{ a }}</a>
  </div>

  <div v-for="(product, i) in products" :key="i">
    <h4>{{ products[i] }}</h4>
    <p>50 만원</p>
    <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{ 신고수[i] }}</span>
  </div>

</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0, 0, 0],
    }
  },
  methods: {
    increase(i){
      this.신고수[i] += 1;
    }
  },
  components: {
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
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
  text-decoration: none;
}
</style>
