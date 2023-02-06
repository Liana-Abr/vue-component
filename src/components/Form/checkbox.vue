<template>
<div class="checkbox">
  <button @click.prevent="seeCheck = !seeCheck" class="check" :style="{display: seeCheck ? 'none' : 'flex' }"></button>
  <button @click.prevent="seeCheck = !seeCheck"  class="check-clicked" :style="{display: seeCheck ? 'flex' : 'none', borderColor: color}">
    <i :style="{color: color}" class="fa-solid fa-check"></i>
  </button>
  <div class="label">{{ label }}</div>
</div>
</template>

<script>
export default {
  name: "checkbox-component",
  props:{
    label: String,
    color: String
  },
  data(){
    return{
      seeCheck: false,
    }
  },
}
</script>

<style>
.checkbox{
  margin: 20px;
  width: 200px;
  display: flex;
}
.check{
  width: 30px;
  border: 2px solid;
  border-radius: 5px;

}
.check:hover{
   background-color: rgba(175, 171, 171, 0.35);
  transition: 0.5s ease-in-out;
 }
.check-clicked{
  width: 30px;
  display: none;
  align-items: center;
  justify-content: center;
  border: 2px solid;
  border-radius: 5px;
}
.label{
  font-size: 20px;
  margin-left: 10px;
  font-family: "Roboto", sans-serif;
}


</style>