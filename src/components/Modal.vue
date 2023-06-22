<template>
    <div class="black-bg" v-if="모달창열렸니">
    <div class="white-bg">
      <img :src="원룸s[누른거].image" style="width: 100%;">
      <h4>{{원룸s[누른거].title}}</h4>
      <p>{{원룸s[누른거].content}}</p>
      <!-- <input @input="month = $event.target.value"> -->
      <input v-model="month">
      <!-- <textarea v-model="month"></textarea>
      <select v-model="month">
        <option>123</option>
        <option>2123</option>
        <option>3123</option>
      </select>
      <input type="checkbox" v-model="month"> -->

      <p> {{ month }}개월 선택함 : {{원룸s[누른거].price * month}} 원</p>
      
      <button @click="$emit('closeModal')">닫기</button>
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
    watch:{
      month(a){
        //입력한 데이터가 13보다 크면 경고문
        if( a > 13 ){
          alert('13 세 이상 만..')
        }
        //month 가 변경 될때 마다 동작
        // 사용자가 month 를 글자로 입력하면  경고문 

      }
    },
    data(){
        return{
          month: '',
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