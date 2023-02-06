<template>
  <h1>Components</h1>
<!--  <header-component/>-->
  <checkbox-component label="Checkbox label" color="#39398c"/>
<!--  <flex-layout-->
<!--      size="sm"-->
<!--  />-->

</template>

<script>
// import FlexLayout from "@/components/component";
// import HeaderComponent from "@/components/header";
import CheckboxComponent from "@/components/Form/checkbox";


export default {
  name: 'App',
  components: {
    CheckboxComponent,
    // HeaderComponent,
    // FlexLayout,

  },

}
</script>
