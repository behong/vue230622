<template>

  <transition name="fade">
    <Modal @closeModal="모달창열렸니 = false" v-bind:원룸s="원룸s" :누른거="누른거" :모달창열렸니="모달창열렸니"/>
  </transition>
  
  <MenuOne/>
  
  <Discount />

  <button @click="priceSort">가격순 정렬</button>

  <!--커스텀 이벤트-->
  <Card @openModal="모달창열렸니 = true; 누른거 =$event" :상품="원룸s[i]" v-for="(작명,i) in 원룸s" :key="작명" />

</template>

<script>
import data from './assets/oneRoom';
import Discount from './components/Discount.vue'
import MenuOne from './components/Menu.vue'
import Modal from './components/Modal.vue'
import Card from './components/Card.vue'


export default {
  name: 'App',
  data(){
    return{
      오브젝트:{name: 'kim',age:20},
      신고수: [0,0,0],
      모달창열렸니: false,
      원룸s: data,
      누른거 : 0,
    }
  },
  methods : {
    increase(susu){
      this.신고수[susu] += 1;
    },
    priceSort(){
      this.원룸s.sort(function(a,b){
        return a.price - b.price
      })
    }
  },
  components: {
    Discount,
    MenuOne,
    Modal,
    Card,
  }
}
</script>

<style>

/* 퇴장 시작(에니메이션) */
.fade-leave-from{
  opacity: 1;
}
.fade-leave-active{
  transition: all 1s;
}

/* 퇴장 끝 (에니메이션) */
.fade-leave-to{
  opacity: 0;
}


/* 시작(에니메이션) */
.fade-enter-from{
  opacity: 0;
}
.fade-enter-active{
  transition: all 1s;
}

/* 끝 (에니메이션) */
.fade-enter-to{
  opacity: 1;
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.room-img{
  width:100%;
  margin-top: 40px;
}

.start{
  opacity: 0;
  transition: all 1s;
}

.end{
  opacity: 1;
}

</style>
