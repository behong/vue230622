<template>
    <div class="black-bg" v-if="모달창열렸니">
    <div class="white-bg">
      <img :src="원룸s[누른거].image" style="width: 100%;">
      <h4>{{원룸s[누른거].title}}</h4>
      <p>{{원룸s[누른거].content}}</p>
      <p>{{원룸s[누른거].price}} 원</p>
      <!-- <button @click="모달창열렸니= false">닫기</button> -->
    </div>
  </div>

</template>

<script>

export default {
    name: 'Modal-one',
    props :{
        원룸s: Array,
        누른거: Number,
        모달창열렸니: Boolean,
    },
    data(){
        return{
        }
  },    
}
</script>

<style>
body{
  margin: 0;
}

div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width:100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>