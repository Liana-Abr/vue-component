<template>
  <div class="date-picker">
<!--    Дата-->
    <div class='custom-select' :class="variant">
      <select>
        <option
            v-for='i in numberOfDays'
            :key='i'
            :value="numberOfDays + (i - 1)">
          {{ i }}
        </option>
      </select>
    </div>
    <!-- Месяц -->
    <div class="custom-select" :class="variant">
      <select>
        <option
            v-for="(month, i) in months"
            :key="month"
            :value="i">
          {{ month }}
        </option>
      </select>
    </div>
    <!-- Год -->
    <div class="custom-select" :class="variant">
      <select>
        <option
            v-for="i in numberOfYears"
            :key="i"
            :value="startingYear + (i - 1)"
        >
          {{ startingYear + (i - 1) }}
        </option>
      </select>
    </div>
  </div>
</template>


<script>
export default {
  name:"datepicker-component",
  data(){
    return{
      months: [
        'Январь',
        'Февраль',
        'Март',
        'Апрель',
        'Май',
        'Июнь',
        'Июль',
        'Август',
        'Сентябрь',
        'Октябрь',
        'Ноябрь',
        'Декабрь',
      ],
      startingYear: 1995,
      numberOfYears: 30,
      numberOfDays: 31
    }
  },
  props:{
    variant:{
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.date-picker{
  margin: 20px;
}
.custom-select {
  border-radius: 5px;
  float: left;
  margin-right: 10px;
  position: relative;
}
.custom-select:hover{
  box-shadow: 0 0 5px -1px;
}

.custom-select select {
  appearance: none;
  background-color: inherit;
  border: none;
  color: #333;
  display: block;
  font-size: 16px;
  height: 32px;
  padding: 5px 30px 5px 10px;
  margin: 0;
  outline: none;
}
.outlined{
  border: 2px solid;
}
.underlined{

  border-bottom: 2px solid;
  border-radius: 0;
}
.shadow{
  box-shadow: 0px 0px 5px -1px #8d8d8d;
}
</style>
