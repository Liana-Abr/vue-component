<template>
  <h1>Components</h1>
<!--  <header-component/>-->
  <checkbox-component label="Checkbox label" color="#39398c"/>
  <input-container
      type="phone"
      variant="outlined"
      label="Введите почту"
  />
  <select-component
      :options="['1', '2', '3', '4']"
      :default="'1'"
      class="select"
  />
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


export default {
  name: 'App',
  components: {
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
