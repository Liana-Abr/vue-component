<template>
  <h1>Component</h1>
<!--  container=>row=>col-->
<!--  size="sm" => flex="10%" -->
  <!--  size="md" => flex="50%" -->
  <!--  size="lg" => flex="100%" -->

  <div class="container">
    <div class="row">
      <div class="column-sm"
           style="background-color:#e74343;"
      >
        <h2>1</h2>
      </div>

      <div class="column-md"
           style="background-color:#6868e7;"
      >
        <h2>2</h2>
      </div>

      <div class="column"
           style="background-color:#87c787;">
        <h2>3</h2>
      </div>

      <div class="column-sm"
           style="background-color:#c38ad5;">
        <h2>4</h2>
      </div>
    </div>
  </div>


</template>

<script>
export default {
  name: 'vue-component',
  props: {
    title: String
  }
}
</script>
<style>

.row {
  display: flex;
  flex-wrap: wrap;

}

.column {
  text-align: center;
  flex: 25%;
  padding: 20px;
}
.column-sm{
  text-align: center;
  flex: 10%;
  padding: 20px;
}
.column-md{
  text-align: center;
  flex: 50%;
  padding: 20px;
}
.column-lg{
  text-align: center;
  flex: 100%;
  padding: 20px;
}

@media screen and (max-width: 992px) {
  .column {
    flex: 50%;
  }
}

@media screen and (max-width: 600px) {
  .row {
    flex-direction: column;
  }
}
</style>