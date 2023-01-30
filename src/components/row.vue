<template>
  <div class="row">
    <la-col
        flex="50"
        style="background-color:#e74343;"
    >1</la-col>
    <la-col
        style="background-color:#6868e7;"
    >2</la-col>
  </div>

</template>
<script>

export default {
  name: "la-row",

}
</script>
<style>
.row {
  display: flex;
  flex-wrap: wrap;

}
@media screen and (max-width: 600px) {
  .row {
    flex-direction: column;
  }
}
</style>