<template>
        <div class="view">
            <img v-bind:src="tour.image" alt="">
            <div>{{tour.title}} 
                <span v-on:click="$emit('modalOpen', tour.id)">[세부내용 보기]</span>
            </div>
            <div>{{tour.price.toLocaleString()}}원</div>
        </div>
</template>

<script>
export default {
    name:'tour',
    props:['tour']
}
</script>

<style>
.view {margin-bottom: 20px;}
</style>