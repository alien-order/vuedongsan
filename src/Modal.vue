<template>
  <div class="black-bg" v-if="모달창열렸니 === true">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <img class="modal-img" :src="원룸들[누른거].image" alt="">
      <p>{{ 원룸들[누른거].content }}</p>
      <input v-model="month">
      <p>{{ month }} 개월 선택함 {{ 원룸들[누른거].price * month }}</p>
      <button @click="close">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal',
    data(){
      return {
        month : 1,
      }
    },
    watch : {
      month(a){
        if (isNaN(a)) {
          alert('문자 입력하지마셈')
          this.month = 1
        }
      },
    },
    props : {
        원룸들 : Array,
        누른거 : Number,
        모달창열렸니 : Boolean,
    },
    methods : {
      close(){
        this.$emit('closeModal')
      }
    }
    
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