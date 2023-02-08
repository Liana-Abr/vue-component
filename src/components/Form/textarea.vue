<template>
<div class="container">
  <label>{{label}}</label>
  <textarea
      :class="variant"
  :style="{backgroundColor: color}">
  </textarea>
</div>
</template>
<script>
export default {
  name: "textarea-component",
  props:{
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
  }
}
</script>
<style scoped>
.container{
  margin: 20px;
}
label{
  position: absolute;
  margin: 5px;
  font-size: 10px;
}
textarea{
  outline: none;
  padding: 20px 5px 0 10px;
  height: 200px;
  width: 300px;
  font-size: 15px;
}
textarea:hover{
  box-shadow: 0px 0px 5px -1px;
}
.outlined{
  border: 2px solid;
}
.underlined{
  box-shadow: -1px -1px 5px -1px #8d8d8d;
  border-bottom: 2px solid;
  border-radius: 0;
}
.shadow{
  box-shadow: 0px 0px 5px -1px #8d8d8d;
}
</style>