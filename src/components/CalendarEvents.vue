<template>
  <div class="calendar" style="width: 100%; display: inline-block;">
    <full-calendar ref="fullCalendar" :options="calendarOptions"></full-calendar>
  </div>
</template>

<script>
import FullCalendar from "@fullcalendar/vue";
import dayGridPlugin from "@fullcalendar/daygrid";
import interactionPlugin from "@fullcalendar/interaction";
import listPlugin from "@fullcalendar/list";
export default {
  name: "calendar-event",
  components: {
    FullCalendar,
  },
  props: {
    options: {
      type: Object,
    },
    preloader: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      calendarOptions: {
        plugins: [dayGridPlugin, interactionPlugin, listPlugin],
        initialView: ["listWeek"],
        timeZone: "UTC",
        dateClick: this.handleDateClick,
        views: {
          listDay: { buttonText: "list day" },
          listWeek: { buttonText: "list week" },
          listMonth: { buttonText: "list month" },
        },
        header: {
          left: "title",
          center: "",
          right: "listDay,listWeek,listMonth",
        },
      },
      events: [
        {
          id: "2302",
          title: "XXX",
          start: "16/4/2021 12:00:00 AM",
          end: "17/4/2021 12:00:00 AM",
          allDay: true,
          url: "xxx",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
.calendar{
  font-family: "Kanit";
  color: rgb(155, 41, 41);
}
h2 {
  margin: 0;
  font-size: 16px;
}
ul {
  margin: 0;
  padding: 0 0 0 1.5em;
}
li {
  margin: 1.5em 0;
  padding: 0;
}
b {
  /* used for event dates/times */
  margin-right: 3px;
}
.demo-app {
  display: flex;
  min-height: 100%;
  font-family: Arial, Helvetica Neue, Helvetica, sans-serif;
  font-size: 14px;
}
.demo-app-sidebar {
  width: 300px;
  line-height: 1.5;
  background: #eaf9ff;
  border-right: 1px solid #d3e2e8;
}
.demo-app-sidebar-section {
  padding: 2em;
}
.demo-app-main {
  flex-grow: 1;
  padding: 3em;
}
.fc {
  /* the calendar root */
  max-width: 1100px;
  margin: 0 auto;
}
</style>
