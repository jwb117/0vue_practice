<template>
  
<div class="black-bg" v-if="tourView == true"> 
  <div class="white-bg">
    <img v-bind:src="tour[listNum].image" alt="">
      <div>{{tour[listNum].title}}</div>
      <div>{{tour[listNum].price.toLocaleString()}}원</div>
      <div>{{tour[listNum].content}}</div>
      <button v-on:click="$emit('modalClose')">창닫기</button>

  </div>
</div>

</template>

<script>
export default {
    name:'modal',
    props:['tourView', 'tour', 'listNum']
}
</script>

<style>

</style>