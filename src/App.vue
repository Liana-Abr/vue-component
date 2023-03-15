<template>
  <h1>Components</h1>
  <header-component/>
  <checkbox-component
      label="Checkbox label"
      color="#39398c"
  />
  <input-component
      type="text"
      variant="outlined"
      label="Введите имя"
  />
  <input-component
      type="text"
      variant="shadow"
      label="Введите имя"
  />
  <input-component
      type="email"
      variant="underlined"
      label="Введите почту"
  />
  <input-component
      type="password"
      variant="underlined"
      label="Введите пароль"
  />

  <select-component
      :options="['1', '2', '3', '4']"
      :default="'1'"
  />
  <textarea-component
      color="white"
      variant="outlined"
      label="Введите что-нибудь..."
  />
  <textarea-component
      color="white"
      variant="underlined"
      label="Введите что-нибудь..."
  />
 <datepicker-component/>

</template>

<script>
// import FlexLayout from "@/components/component";
import HeaderComponent from "@/components/header";
import CheckboxComponent from "@/components/Form/checkbox";
import SelectComponent from "@/components/Form/select";
import TextareaComponent from "@/components/Form/textarea";
import DatepickerComponent from "@/components/datepicker";
import InputComponent from "@/components/Form/input";



export default {
  name: 'App',
  components: {
    InputComponent,
    DatepickerComponent,
    TextareaComponent,
    SelectComponent,
    CheckboxComponent,
    HeaderComponent,
    // FlexLayout,

  },

}
</script>
<style>
*{
  font-family: 'Sofia Sans', sans-serif;
}
</style>
