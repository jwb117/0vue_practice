<template>
  <div class="header">
      {{text}}
  </div>
</template>

<script>
export default {
    name:'main',
    data(){
        return{
            text:"싱가포르 투어를 선택해보세요!"
        }
    }
}
</script>

<style>
    .header{height: 170px; width: 100%; background: rgb(20, 218, 185); display: flex; justify-content: center; align-items: center; margin-bottom: 20px;}
</style>