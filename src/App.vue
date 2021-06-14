<template>
  
  <top-header/>

  <!-- <div>
    <ul class="view">
      <li v-for="(item, i) in tour" v-bind:key="i" >
        <img v-bind:src="tour[i].image" alt="">
        <div>{{tour[i].title}} <span v-on:click="tourView=true; listNum=i">[세부내용 보기]</span></div>
        <div>{{tour[i].price.toLocaleString()}}원</div>
      </li>
    </ul>
  </div> -->
<tour v-bind:tour="tour[i]" v-for="(item, i) in tour" v-bind:key="i" @modalOpen="tourView=true; listNum=$event"/>


<!-- <div class="black-bg" v-if="tourView == true"> 
  <div class="white-bg">
    <img v-bind:src="tour[listNum].image" alt="">
      <div>{{tour[listNum].title}}</div>
      <div>{{tour[listNum].price.toLocaleString()}}원</div>
      <div>{{tour[listNum].content}}</div>
      <button v-on:click="tourView=false">창닫기</button>

  </div>
</div> -->

<div class="start" v-bind:class="{end:tourView}">
  
    <modal v-bind:tour="tour" v-bind:tourView="tourView" v-bind:listNum="listNum" @modalClose="tourView=false"></modal>
  
</div>


</template>

<script>
import singapore from './data.js'
import main1 from './components/header.vue'
import modal from './components/modal.vue'
import tour from './components/tour.vue'


export default {
  name: 'App',
  data(){
    return{
      tour:singapore,
      listNum:0,
      tourView:false,
      
    }
  },
  components: {
    'top-header':main1,
    modal:modal,
    tour:tour,
    
  }
}
</script>

<style>
html, body{height: 100%;}
*{margin: 0; padding: 0;}
li{list-style: none;}
img{width: 100%;}

.black-bg{width: 100%; position: fixed; background: rgba(0,0,0,0.7); top:0; height: 100%; display: flex; justify-content: center; align-items:center;}
.white-bg{width: 80%; background: #fff; border-radius: 10px; padding: 20px;}

.start{opacity:0; transition:1s;}
.start.end{opacity:1;}

.close{opacity: 1; transition: 1s;}
.close.end{opacity: 0;}
</style>
