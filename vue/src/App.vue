<script setup>
 import Info from '@/components/cards.vue' //import Cards 
 const props = defineProps({
   Info : Object
 })
 </script>
<template> 
 <!-- <div class="Card"> <h1 class="text">{{ Name }}<img class="img" :src="IMG"> <button class="btn" type="button">Select</button>  </h1></div> -->
    <h1> Welcome to Evan's Draft Game</h1>
    <h1 v-for="players in Info">  
     {{players.Name}}
    </h1>

</template>





<!--  <template>
    <div class="Card"> <h1 class="text">{{ Name }}<img class="img" :src="Image"> <button class="btn" type="button">Select</button>  </h1></div>
</template>
<script setup>
const props = defineProps({
   Name: String,
    Image : String,
})
</script>
<style lang="scss" scoped>
</style> --> 