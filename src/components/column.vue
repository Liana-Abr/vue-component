<template>
  <div class="col"
       :style="{'flex': flex + '%'}"
  >

  </div>

</template>
<script>
export default {
  name: "la-col",
  props: ['flex']
}
</script>
<style>
.col {
  background-color: #6868e7;
  text-align: center;
  padding: 20px;
  flex: 25%;

}
@media screen and (max-width: 992px) {
  .col{
    flex: 50%;
  }
}

</style>