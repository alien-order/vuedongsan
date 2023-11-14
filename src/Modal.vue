<template>
  <div class="black-bg" v-if="모달창열렸니 === true">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <img class="modal-img" :src="원룸들[누른거].image" alt="">
      <p>{{ 원룸들[누른거].price }}</p>
      <p>{{ 원룸들[누른거].content }}</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal',
    props : {
        원룸들 : Array,
        누른거 : Number,
        모달창열렸니 : Boolean,
    },
    
}
</script>

<style>
.modal-img {
  width: 100%;
  height: 100%;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>