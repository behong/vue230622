<template>
    <div class="discount">
        <h4> 지금 결제하면 {{salePer}}% 할인</h4>
    </div>  
</template>

<script>
export default {
    name: 'Discount-one',
    data(){
        return{
            salePer : 30
        }
    },
    mounted(){
    // setTimeout(() =>{
    //   //배너 닫아줘 
    //   this.showDiscount = false;
    // },2000)
    //1 초마다 1% 낮아진다.
    setInterval(() => {
        if(this.salePer > 1){
            this.salePer--;
        }
    }, 1000);
  },    
}
</script>

<style>
.discount{
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>