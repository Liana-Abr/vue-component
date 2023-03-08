<template>
<div class="container">
  <div class="select">
    <div v-if="clickedWord === ''">
      {{ new Date().getDate() }} / {{ currMonth+1 }} /{{currYear}}
    </div>
    <div v-else>
      {{clickedWord}}/{{ currMonth+1 }} /{{currYear}}
    </div>

    <button @click.prevent='seeCalendar =!seeCalendar '>
      <i class="fa-regular fa-calendar"></i>
    </button>

  </div>


  <div class="wrapper" :style="{display: seeCalendar ? 'block' : 'none' }">
    <header>
      <button :style="{display: months[currMonth]==='Январь' ? 'none': 'flex' }"
              class="icons"
              @click="prev">
        <i class="fa-solid fa-chevron-left"></i>
      </button>

      <p class="current-date" :class="months[currMonth]=== 'Декабрь'? 'date-right' : 'current-date'">
        {{ months[currMonth] }} {{currYear}}
      </p>
      <div class="icons-years">
          <button class="icons-up"  :style="{left: months[currMonth]==='Декабрь' ? '40%' : '65%'}" @click="prevM">
            <i class="fa-solid fa-chevron-up"></i>
          </button>
          <button class="icons-down" :style="{left: months[currMonth]==='Декабрь' ? '40%' : '65%'}" @click="nextM">
            <i class="fa-solid fa-chevron-down"></i>
          </button>
      </div>

      <button :style="{display: months[currMonth]==='Декабрь' ? 'none': 'flex' }"
              class="icons"
              @click="next">
        <i class="fa-solid fa-chevron-right"></i>
      </button>
    </header>
    <div class="calendar">
      <ul class="weeks">
        <li v-for="w in weeks" :key="w">
          {{ w }}
        </li>
      </ul>

        <div class="dates d-flex">
          <p  class="day" v-for="day in firstDayOfMonth" :key="day">{{}}</p>
          <p :style="{color: todayDate(date) ? '#0084ff' : 'black' }"
             :class="date===todayDate() ? 'text-primary' : ''" class="day"
             v-for="date in lastDateOfMonth"
             :key="date"
             @click="clickedWord = date"
          >
            {{date}}
          </p>
        </div>
    </div>
  </div>

</div>
</template>

<script>

export default {
  name: "datepicker-component",
  data(){
    return{
      clickedWord: '',
      seeCalendar: false,
      currYear: new Date().getFullYear(),
      currMonth: new Date().getMonth(),
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
      weeks:[
        'Пн',
        'Вт',
        'Ср',
        'Чт',
        'Пт',
        'Сб',
        'Вс'
      ],
    }
  },
  computed:{
    firstDayOfMonth(){
      return new Date(this.currYear, this.currMonth, 0).getDay();
    },
    lastDateOfMonth(){
      return new Date(this.currYear,this.currMonth+1,0).getDate()
    }
  },

  methods:{
    prevM(){
      this.currYear--
    },
    nextM(){
      this.currYear++
    },
    prev(){
      this.currMonth--
    },
    next(){
      this.currMonth++
    },
    todayDate(date){
     let calendarDate=new Date(this.currYear, this.currMonth, date).toDateString()
      let toDay=new Date().toDateString()
      return calendarDate===toDay ? "text-primary" : ""
    },
  }
}
</script>

<style scoped>
.container{
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
body{
  display: flex;
  align-items: center;
  justify-content: center;
  background: #0084ff;
}
.weeks p, .dates p{
  width: 14.28%;
}

.dates{
  flex-wrap: wrap;
  display: flex;
}
.wrapper{
  margin-top: 5px;
  border-radius: 10px;
  width: 470px;
  background: #fff;
  border: 2px solid black;
}
.wrapper header {
  position: relative;
  border-radius: 8px 8px 0 0;
  background-color: #0084ff;
  display: flex;
  height: 72px;
  align-items: center;
  padding: 0 40px 0;
  justify-content: space-between;
}
header button{
  color: white;
}

header .icons{
  font-size: 15px;
  padding: 10px;
  border-radius: 5px;
}
header button:hover{
  background: rgba(252, 252, 252, 0.24);
  color: white;
}
header .current-date{
  font-size: 1.45rem;
  font-weight: 700;
  color: white;
}
header .date-right{
  margin-left: 200px;
}
header .icons button{
  color: white;
  cursor: pointer;
   margin: 20px;
  padding: 10px;
}
header .icons button:hover{
  background: rgba(252, 252, 252, 0.24);
  border-radius: 10px;
}

.icons-years{
  display: flex;
  flex-direction: column;
}
.icons-years i{
  font-size: 10px;
}

.icons-up{
  position: absolute;
  top: 20%;
}
.icons-up:hover{
  background: rgba(252, 252, 252, 0.24);
  border-radius: 5px;
  height: 20px;
}

.icons-down{
  position: absolute;
  left: 65%;
  top: 45%;
}
.icons-down:hover{
  background: rgba(252, 252, 252, 0.24);
  border-radius: 5px;
  height: 20px;
}

.calendar ul{
  display: flex;
  list-style: none;
  flex-wrap: wrap;
  text-align: center;
}

.calendar .weeks li{
  margin: 18px;
  display: flex;
  justify-content: space-between;
  font-weight: 500;
  color: black;
}
.calendar{
  padding: 5px 20px;
}

.calendar .day{
  cursor: pointer;
  margin-bottom: 10px;
  display: flex;
  justify-content: center;
  color: black;
}
.calendar .day:hover{
  background: rgba(206, 206, 206, 0.36);

}


</style>