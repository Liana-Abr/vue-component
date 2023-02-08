<template>
<!--  Виды: текст, почта, пароль-->
  <!--  Стили: outlined( с границами ),без пропса обычное поле, underlined( с нижнем подчеркиванием), shadow(с тенью)-->
  <div class="container">
      <label>{{label}}</label>
      <input :class="variant" :style="{borderColor: color}" :type='type'>
  </div>
</template>
<script>
export default {
  name: "input-container",
  props:{
    type: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      required: false,
    },
    variant: {
      type: String,
      required: true,
    },
  },
}
</script>
<style scoped>
.container{
  width: 200px;
  margin: 20px;
  display: flex;
  flex-direction: column;
}
label{
  font-weight: bold;
  font-size: 15px;
  transition: 0.7s ease;
}
input{
  outline: none;
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
  box-shadow: 2px 2px 2px #8d8d8d;
}

</style>