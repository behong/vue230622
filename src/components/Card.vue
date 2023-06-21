<template>
    <!-- <div v-for="(상품,i) in 원룸s" :key='i'> -->
    <div>
    <img :src="상품.image" class="room-img">
    <h4 >{{상품.title}}  원룸 </h4> 
    <!-- <h4 @click="모달창열렸니 = true; 누른거 = i">{{상품.title}}  원룸 </h4> -->
    <p>{{상품.price}} 원</p>
  </div>
</template>

<script>
export default {
    name: 'Card-one',
    props:{
        상품:Object,
    }
}
</script>

<style>

</style>