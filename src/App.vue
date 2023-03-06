<template>
  <h1>Components</h1>
<!--  <header-component/>-->
  <checkbox-component
      label="Checkbox label"
      color="#39398c"
  />
  <input-container
      type="text"
      variant="outlined"
      label="Введите имя"
  />
  <input-container
      type="text"
      variant="shadow"
      label="Введите имя"
  />
  <input-container
      type="email"
      variant="underlined"
      label="Введите почту"
  />
  <input-container
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
<!--  <datepicker-component-->
<!--      variant="shadow"-->
<!--  />-->
<!--  <datepicker-component-->
<!--      variant="underlined"-->
<!--  />-->
<!--  <datepicker-component-->
<!--      variant="outlined"-->
<!--  />-->
<!--  <calendar-component/>-->
<!--  <flex-layout-->
<!--      size="sm"-->
<!--  />-->

</template>

<script>
// import FlexLayout from "@/components/component";
// import HeaderComponent from "@/components/header";
import CheckboxComponent from "@/components/Form/checkbox";
import InputContainer from "@/components/Form/input";
import SelectComponent from "@/components/Form/select";
import TextareaComponent from "@/components/Form/textarea";
// import DatepickerComponent from "@/components/Form/datePicker";
// import CalendarComponent from "@/components/Form/calendar";


export default {
  name: 'App',
  components: {
    // CalendarComponent,
    // DatepickerComponent,
    TextareaComponent,
    SelectComponent,
    InputContainer,
    CheckboxComponent,
    // HeaderComponent,
    // FlexLayout,

  },

}
</script>
<style>
*{
  font-family: 'Sofia Sans', sans-serif;
}
</style>
