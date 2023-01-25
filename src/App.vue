<template>
  <v-app>
    <v-main>
      <vue-component />
    </v-main>
  </v-app>
</template>

<script>
import VueComponent from "@/components/component";

export default {
  name: 'App',
  components: {
    VueComponent,
  },

}
</script>
