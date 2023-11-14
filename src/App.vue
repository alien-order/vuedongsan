<template>
  <div class="menu">
    <a href="" v-for="(a, i) in 메뉴들" :key="i">{{ a }}</a>
  </div>

  <Modal :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>
  <Card :원룸="원룸" v-for="(원룸, i) in 원룸들" :key="i"/>
    <!-- <img :src="원룸.image" alt="">
    <h4 @click="모달창열렸니 = true; 누른거 = i">{{ 원룸.title }}</h4>
    <p>{{ 원룸.price }}</p> -->
 

</template>

<script>
import Discount from './Discount.vue';
import data from './oneroom';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data(){
    return {
      오브젝트 : { name : 'kim', age : 20 },
      누른거 : 0,
      모달창열렸니 : false,
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      모달아이템 : { title : '1', content : '2' },
      원룸들 : data,
    }
  },
  methods: {
    increase(i){
      this.신고수[i] += 1;
    },
  },
  components: {
    Discount,
    Modal,
    Card,
  }
}
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

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
