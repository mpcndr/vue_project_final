<template>
  <div id="calendar">
    <app-component></app-component>
    <div class="header">
      <i
        class="nc-icon-outline arrows-1_minimal-left left"
        v-on:click="previous()"
      ></i>
      <span>{{ month.format("MMMM, YYYY") }}</span>
      <i
        class="nc-icon-outline arrows-1_minimal-right right"
        v-on:click="next()"
        >></i
      >
    </div>
    <div class="names">
      <span class="day">Su</span>
      <span class="day">Mo</span>
      <span class="day">Tu</span>
      <span class="day">We</span>
      <span class="day">Th</span>
      <span class="day">Fr</span>
      <span class="day">Sa</span>
    </div>
    <div class="weeks">
      <div class="week" v-for="week in weeks" :key="week">
        <span
          class="day"
          v-for="day in week.days"
          v-on:click="setDate(day.date)"
          v-bind:class="{
            today: day.isToday,
            'different-month': !day.isCurrentMonth,
            selected: day.date.isSame(this.selected),
          }"
          :key="day"
          >{{ day.number }}</span
        >
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";
export default {
  el: "#calendar",
  name: "calendarevents",
  data: function() {
    return {
      weeks: [],
      date: moment(),
    };
  },
  computed: {
    month() {
      return moment(this.date).clone();
    },
    start() {
      return moment(this.date).clone();
    },
  },
  created: function() {
    this.selected = this.date
      .hour(0)
      .minute(0)
      .second(0)
      .millisecond(0);
    this.month = this.selected.clone();
    this.start = this.selected.clone();
    this.start.date(1);
    this.removeTime(this.start.day(0));
    this.buildMonth(this.start, this.month);
  },
  methods: {
    removeTime: function(date) {
      return date
        .day(0)
        .hour(0)
        .minute(0)
        .second(0)
        .millisecond(0);
    },
    buildWeek: function(date, month) {
      let days = [];
      for (var i = 0; i < 7; i++) {
        days.push({
          name: date.format("dd").substring(0, 1),
          number: date.date(),
          isCurrentMonth: date.month() === month.month(),
          isToday: date.isSame(new Date(), "day"),
          date: date,
        });
        date = date.clone();
        date.add(1, "d");
      }
      return days;
    },
    buildMonth: function(start, month) {
      this.weeks = [];
      var done = false,
        date = start.clone(),
        monthIndex = date.month(),
        count = 0;
      while (!done) {
        this.weeks.push({ days: this.buildWeek(date.clone(), month) });
        date.add(1, "w");
        done = count++ > 2 && monthIndex !== date.month();
        monthIndex = date.month();
      }
    },
    next: function() {
      let next = this.month.clone();
      this.removeTime(next.month(next.month() + 1).date(1));
      this.month.month(this.month.month() + 1);
      this.buildMonth(next, this.month);
      this.selected = this.selected.month(this.selected.month() + 1).date(1);
      this.setDate(this.selected.toDate());
    },
    previous: function() {
      let previous = this.month.clone();
      previous = this.removeTime(previous.month(previous.month() - 1).date(1));
      this.month.month(this.month.month() - 1);
      this.buildMonth(previous, this.month);
      this.selected = this.selected.month(this.selected.month() - 1).date(1);
      this.setDate(this.selected.toDate());
    },
    setDate(newDate) {
      this.selected = newDate;
    },
  },
  mounted: function() {
      
  },
};
</script>

<style scoped>
#calendar {
  display: block;
  margin-top: 20px;
  user-select: none;
  font-size: 0;
  width: 300px;
  font-family: "Kanit";
}
#calendar > .header {
  width: 100%;
  height: 40px;
  color: #82687e;
  font-size: 0;
}

#calendar * {
  height: 40px;
  line-height: 40px !important;
  display: inline-block;
  vertical-align: middle;
}

#calendar > i {
  width: 10%;
  position: relative;
  cursor: pointer;
  display: inline-block;
  font-size: 22px;
  color: #e4e2e9;
}

#calendar > i.left {
  text-align: left;
  user-select: none;
}
#calendar > i.right {
  text-align: right;
  user-select: none;
}

#calendar > span {
  width: 80%;
  font-weight: bold;
  text-align: center;
  color: inherit;
  font-size: 18px;
  font-weight: 600;
  user-select: none;
}

.name {
  margin: 25px 0 0;
  font-size: 0;
}
.name > span {
  width: (100%/7);
  font-size: 0.75em;
  text-align: center;
  height: 50px;
  line-height: 50px;
  display: inline-block;
  vertical-align: middle;
  color: #82687e;
  font-size: 14px;
  user-select: none;
}

.week > span.day {
  width: (100%/7);
  font-weight: 700;
  font-size: 14px;
  text-align: center;
  height: 45px;
  line-height: 45px;
  display: inline-block;
  vertical-align: middle;
  background: white;
  cursor: pointer;
  color: black;
  color: #82687e;
  user-select: none;
  box-shadow: inset 0.5px 0.5px 0.5px 0.5px #e4e2e9;
}
.week > span.day:last-child {
  box-shadow: inset 0 0.5px 0 0.5px #e4e2e9;
}
.week > span.day > .different-month {
  background-color: #f4f3f6;
}
.week > span.day > .selected {
  color: #06a99c;
  border: 1px solid #06a99c;
  border-bottom: 1px solid #06a99c !important;
}
.week:last-child > span.day {
  border-bottom: 1px solid #e4e2e9;
}
</style>
