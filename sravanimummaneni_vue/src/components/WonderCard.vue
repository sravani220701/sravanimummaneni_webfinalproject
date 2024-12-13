<template>
    <div v-for="wonder in wonders" :key="wonder.id" class="wonder-card">
      <SingleWonder :wonders="wonder" />
    </div>
</template>

<script>
import SingleWonder from './SingleWonder.vue'
export default {
    name: 'WonderCard',
    props:{
        wonders: Array
    },
    components:{
        SingleWonder
    }
}
</script>

<style>
.wonder-card {
  width:21%;
  padding:16px;
  border:2px solid #94c2e8;
  border-radius:8px;
  background-image:linear-gradient(15deg,#FFDEE9 0%,#caf9f8 100%,#ffffff 0%,#ffffff 0%);
  box-shadow:2px 4px 8px rgba(0,0,0,0.8); 
  transition:transform 0.2s,box-shadow 0.2s;
}
.wonder-card:hover {
  transform:scale(1.05);
  box-shadow:0 8px 16px rgba(0,0,0,0.2); 
}
</style>