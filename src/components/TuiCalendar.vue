<template>
  <calendar style="height: 500px;" />
</template>

<script>
import "tui-calendar/dist/tui-calendar.css";
import "tui-date-picker/dist/tui-date-picker.css";
import "tui-time-picker/dist/tui-time-picker.css";
import { Calendar } from "@toast-ui/vue-calendar";
export default {
  name: "TuiCalendar",
  components: {
    calendar: Calendar,
  },
  data() {
    return {
      data_Cal: [
        {
          id: "1",
          calendarId: "1",
          title: "my schedule",
          category: "time",
          dueDateClass: "",
          start: "2021-04-18T22:30:00+09:00",
          end: "2021-04-19T02:30:00+09:00",
        },
      ],
      view: "month",
      scheduleView: ["time"],
      theme: {
        "month.dayname.height": "30px",
        "month.dayname.borderLeft": "1px solid #ff0000",
        "month.dayname.textAlign": "center",
        "week.today.color": "#333",
        "week.daygridLeft.width": "100px",
        "week.timegridLeft.width": "100px",
      },
      week: {
        narrowWeekend: true,
        showTimezoneCollapseButton: true,
        timezonesCollapsed: false,
      },
      month: {
        visibleWeeksCount: 6,
        startDayOfWeek: 1,
      },

      isReadOnly: false,
      useCreationPopup: true,
      useDetailPopup: false,
    };
  },
  methods: {},
  created() {},
};
</script>

<style scoped>
#calendar {
  width: 50%;
}
</style>
