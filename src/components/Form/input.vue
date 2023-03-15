<template>
<!--  Виды: текст, почта, пароль-->
  <!--  Стили: outlined( с границами ),без пропса обычное поле, underlined( с нижнем подчеркиванием), shadow(с тенью)-->
  <div class="container">
      <label>{{label}}</label>
    <!-- Если тип input пароль -->
    <div v-if="type === 'password'" :class="variant" class="inp-password">
      <input v-if="showPassword" type="text" v-model="password" />
      <input v-else type="password"  v-model="password">
      <button class="button" @click="toggleShow">
        <span class="icon is-small is-right">
            <i :class="{ 'fa-regular fa-eye-slash': showPassword, 'fa-regular fa-eye': !showPassword }"/>
        </span>
      </button>
    </div>

    <!-- Остальной тип input -->
    <div  v-else-if="type !== 'password'" class="inp">
      <input :class="variant" :style="{borderColor: color}" :type='type'/>
    </div>


  </div>
</template>
<script>
export default {
  name: "input-component",
  props:{
    type: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: false,
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
  data() {
    return {
      showPassword: false,
      password: null
    };
  },
  methods: {
    toggleShow() {
      this.showPassword = !this.showPassword;
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
label{
  font-weight: bold;
  font-size: 15px;
  transition: 0.7s ease;
}
.inp input{
  outline: none;
  width: 200px;
  padding: 2px;
  /*border-radius: 5px;*/
  /*border: 2px solid #e1e1e1;*/
}
.inp-password{
  padding: 2px;
  width: 250px;
  display: flex;

}
.inp-password input{
  outline: none;
  width: 200px;
}
.inp-password i{
  margin-left: 15px;
}
.outlined{
  border: 2px solid;
  border-radius: 5px;
}
.underlined{
  border-bottom: 2px solid black;
  border-radius: 0;
}
.shadow{
  border-radius: 5px;
  border: 2px solid #e1e1e1;
  box-shadow: 2px 2px 2px #8d8d8d;
}

</style>
