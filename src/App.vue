<template>

  <Modal v-bind:원룸s="원룸s" :누른거="누른거" :모달창열렸니="모달창열렸니"/>

  <MenuOne/>
  
  <Discount />
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


</style>
