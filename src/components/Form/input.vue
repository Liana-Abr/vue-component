<template>
<!--  Виды: текст, почта, пароль-->
  <!--  Стили: outlined( с границами ),без пропса обычное поле, underlined( с нижнем подчеркиванием), shadow(с тенью)-->
  <div class="container"  @mouseout="seeLabel=!seeLabel" @mouseenter="seeLabel = !seeLabel">
      <label :style="{display: seeLabel ? 'flex' : 'none' }">{{label}}</label>
      <input :class="variant" :style="{borderColor: color}" :type='type'>
  </div>
</template>
<script>
export default {
  name: "input-container",
  props:{
    type: String,
    label: String,
    color: String,
    variant: String
  },
  data(){
    return{
      seeLabel: false
    }
  }
}
</script>
<style scoped>
.container{
  width: 200px;
  margin: 20px;
  display: flex;
  flex-direction: column;
}
button{
  width: 200px;
  background-color: #0084ff;
}
label{
  font-weight: bold;
  font-size: 15px;
  display: none;
  transition: 0.7s ease;
}
input{
  width: 200px;
  padding: 2px;
  border-radius: 5px;
  border: 2px solid #e1e1e1 ;
}
.outlined{
  border: 2px solid;
}
.underlined{
  border-bottom: 2px solid;
  border-radius: 0;
}
.shadow{

}

</style>