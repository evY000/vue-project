
 <script setup>
 import { reactive } from 'vue'
 import Info from '@/components/cards.js'  

const cart = reactive([])
const props = defineProps({
  Name : String,
   IMG : String, 
})
function Delete(){
  const member = document.getElementById('Members')
  const descrip = document.getElementById('description')
  
  member.remove()
  descrip.remove();
}
  function Move(item){
  cart.push(item)
  const txts = document.getElementById('txt')
  const playerimg = document.getElementById('img')
  const buttons = document.getElementById ('SelectButton')
  txts.remove()
  playerimg.remove()
  buttons.remove()
  }
 </script>
<template> 
<Info :Name="Name" :IMG="IMG"/>
<h1 class="Team">Your team</h1>
<button class="btn" @click="Delete()"> Delete Recent</button>
<div class ='Select' id="Select">
 <h1 class="description" v-for="item in cart" id='description'>
{{ item.Name }} 
<img class="Members" id="Members" :src="item.IMG">
</h1>

</div>
<h1 class="intro"> Welcome to Evan's Draft Game</h1>
<div class='card' id='card'> 
  <h1 class="txt" id="txt" v-for="item in Info"> {{item.Name}}
     <img class="img"  id='img':src="item.IMG"> <button class="btn" id="SelectButton" type="button" @click="Move(item)">Select </button>
  </h1> </div>

</template> 














<style>
.description{
 margin-right: auto;
  font-family:'Courier New', Courier, monospace;
  color:cornflowerblue

}
body{
  background-color: #000000;
}
.Members{
 margin-right: auto;
  height:200px;
  width:275px;
  display: flex;
  border: 20px;
  border-style:solid;
border-color: rgb(37, 87, 107);

}
.Team{
  font-family:'Courier New', Courier, monospace;
  color:cornflowerblue
}
.txt, .intro{
  text-align: center;
  font-family:'Courier New', Courier, monospace;
  color:cornflowerblue
}
.img{
  height:200px;
  width:275px;
  display: grid;
  margin-left: auto;
  margin-right: auto;
  border: 20px;
  border-style:solid;
border-color: rgb(37, 87, 107);
}
.card{
text-align: center;
display:grid;
}
.btn{
display: inline-block;
outline: none;
cursor: pointer;
font-size: 14px;
line-height: 1;
border-radius: 500px;
transition-property: background-color,border-color,color,box-shadow,filter;
transition-duration: .3s;
border: 1px solid transparent;
letter-spacing: 2px;
min-width: 160px;
text-transform: uppercase;
white-space: normal;
font-weight: 700;
text-align: center;
padding: 17px 48px;
color: #3997f6;
background-color: #292730;
height: 48px;
:hover{
      transform: scale(1.04);
      background-color: #292730;
                    }
                  } 
                 /*  spotify buttons from copy-paste css.com */
</style>
