<template>
  <div class="container">
    <div class="select">
      {{ date }}
      <button @click.prevent='seeCalendar =!seeCalendar '>
        <i class="fa-regular fa-calendar"></i>
      </button>

    </div>



<!--    <div class="calendar-block" :style="{display: seeCalendar ? 'flex' : 'none' }">-->
      <div class="calendar-block" >
      <div class="month">
        <button><div class="prev">&#10094;</div></button>
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
        <button @click.prevent="" ><div class="next">&#10095;</div></button>
      </div>
<!--          <button><div class="prev">&#10094;</div></button>-->
<!--            <span>-->
<!--                <div class="custom-select" :class="variant">-->
<!--                  <select>-->
<!--                    <option-->
<!--                        v-for="i in numberOfYears"-->
<!--                        :key="i"-->
<!--                        :value="startingYear + (i - 1)"-->
<!--                    >-->
<!--                      {{ startingYear - (i - 1) }}-->
<!--                    </option>-->
<!--                  </select>-->
<!--                </div>-->
<!--              {{ months[new Date().getMonth()]}}-->
<!--            </span>-->
<!--          <button @click.prevent="" ><div class="next">&#10095;</div></button>-->
<!--      </div>-->

      <ul class="weekdays" >
        <li v-for="w in week" :key="w">{{ w }}</li>
      </ul>

      <ul class="days">
        <li v-for="item in 31" :key="item">
          <button > {{ item }}</button>
        </li>
      </ul>

<!--        <li><span class="active">10</span></li>-->


    </div>
  </div>


</template>

<script>

export default{
    name: "calendar-component",
    data() {
      return {
        seeCalendar: false,
        date: `${new Date().getDate()}/${new Date().getMonth()+1}/${new Date().getFullYear()}`,
        nowMonth: new Date().getMonth(),
        nowYear: new Date().getFullYear(),
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
        week:[
          'Пн',
          'Вт',
          'Ср',
          'Чт',
          'Пт',
          'Сб',
          'Вс'
        ],
        startingYear: new Date().getFullYear(),
        numberOfYears: 30,
        numberOfDays: 31,
        methods: {
          nextMonth(){
            // {{ months[new Date().getMonth()]}}
            this.months[new Date().getMonth()+1]
          }
        }
      }
  },
}
</script>

<style scoped>
.container{
  font-family: 'Sofia Sans', sans-serif;
  margin: 20px;
}
.select{
  border: 2px solid;
  border-radius: 5px;
  width: 150px;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 15px;
}
.select i:hover{
  color: #0084ff;
}

.calendar-block{
  position: relative;
  /*display: none;*/
  display: flex;
  width: 60%;
  flex-direction: column;
  margin-top: 10px;
}

ul {list-style-type: none;}
body {font-family: Verdana, sans-serif;}

.month {
  color: white;
  display: flex;
  border-bottom: 1px solid lightgray;
  gap: 20px;
  justify-content: center;
  align-items: center;
  padding: 20px 25px;
  width: 30%;
  text-transform: uppercase;
  background: #0084ff;
}


.month ul {
  margin: 0;
  padding: 0;
}

.month ul li {
  color: white;
  font-size: 20px;
  text-transform: uppercase;
  letter-spacing: 3px;
}

.month .prev {
  float: left;
  padding-top: 10px;
}

.month .next {
  float: right;
  padding-top: 10px;
}
.month span{
  display: flex;
  align-items: center;
}

.weekdays {
  width: 30%;
  margin: 0;
  padding: 10px 0;
  background-color: #ddd;

}

.weekdays li {
  display: inline-block;
  width: 13.6%;
  color: #666;
  text-align: center;
}

.days {
  width: 30%;
  padding: 10px 0;
  background: #eee;
  margin: 0;
}

.days li {
  list-style-type: none;
  display: inline-block;
  width: 13.6%;
  text-align: center;
  margin-bottom: 5px;
  font-size:12px;
  color: #777;
}

.days li .active {
  padding: 5px;
  background: #0084ff;
  color: white !important
}
.days button:hover{
  background: #0084ff;
  width: 30px;
  color: white;
}
.custom-select {
  display: flex;
  color: white;
  border-radius: 5px;

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
  color: white;
  display: block;
  font-size: 16px;
  height: 32px;
  padding: 5px;
  margin: 0;
  outline: none;
}

</style>