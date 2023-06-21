<template>
    <div class="menu">
        <a v-for="(작명,i) in menus" :key="i">{{작명}}</a>
    </div>
</template>

<script>
export default {
    name: 'Menu-one',
    data(){
        return {
            menus:['Home','Products','About'],
        }
    }
}
</script>

<style>
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;

}
.menu a{
  color: white;
  padding: 10px;
}

</style>