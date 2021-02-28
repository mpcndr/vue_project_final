<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-xs-6 col-md-6 col-lg-6 col-xl-6">
        <!-- <h4>Countdown Time</h4> -->
        <div id="clockdiv">
          <h2>เหลือเวลา</h2>
          <div>
            <span class="days"></span>
            <div class="smalltext">Days</div>
          </div>
          <div>
            <span class="hours"></span>
            <div class="smalltext">Hours</div>
          </div>
          <div>
            <span class="minutes"></span>
            <div class="smalltext">Minutes</div>
          </div>
          <div>
            <span class="seconds"></span>
            <div class="smalltext">Seconds</div>
          </div>
          <h4 class="text-cal">ถึง <span class="text-span">{{ event_data }}</span></h4>
        </div>
      </div>
      <div class="col-xs-6 col-md-6 col-lg-6 col-xl-6">
        <div class="table-responsive">
          <table
            id="dtBasicExample"
            class="table table-striped table-bordered table-sm table-hover"
            cellspacing="0"
            width="100%"
          >
            <thead>
              <tr>
                <th class="th-sm1">รายการ</th>
                <th class="th-sm1">วันที่</th>
              </tr>
            </thead>
            <tbody id="tableList">
              <tr
                v-for="date in dates"
                :key="date.no"
                v-on:click="selectCalendar(date.event)"
              >
                <td>
                  {{ date.event }}
                </td>
                <td>{{ date.date_start }} - {{ date.date_end }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'calendar-data',
  data() {
    return {
      event_data: "เปิดให้ลงทะเบียน",
      dates: [
        {
          no: 1,
          date_start: "26 พ.ย. 2563",
          date_end: "6 ธ.ค. 2563",
          event: "เปิดให้ลงทะเบียน",
        },
        {
          no: 2,
          date_start: "7 ธ.ค. 2563",
          date_end: "21 ธ.ค. 2563",
          event: "ช่วงวันทำการเพิ่ม/ถอน",
        },
        {
          no: 3,
          date_start: "7 ธ.ค. 2563",
          date_end: "11 เม.ย. 2564",
          event: "วันเปิดภาคเรียน",
        },
        {
          no: 4,
          date_start: "23 ม.ค. 2564",
          date_end: "6 ก.พ. 2564",
          event: "สอบกลางภาค",
        },
        {
          no: 5,
          date_start: "29 มี.ค. 2564",
          date_end: "10 เม.ย. 2564",
          event: "สอบปลายภาค",
        },
      ],
      date: [],
    };
  },
  methods: {
    countdownTime: function() {

      function getTimeRemaining(endtime) {
        const total = Date.parse(endtime) - Date.parse(new Date());
        const seconds = Math.floor((total / 1000) % 60);
        const minutes = Math.floor((total / 1000 / 60) % 60);
        const hours = Math.floor((total / (1000 * 60 * 60)) % 24);
        const days = Math.floor(total / (1000 * 60 * 60 * 24));

        return {
          total,
          days,
          hours,
          minutes,
          seconds,
        };
      }

      function initializeClock(id, endtime) {
        const clock = document.getElementById(id);
        const daysSpan = clock.querySelector(".days");
        const hoursSpan = clock.querySelector(".hours");
        const minutesSpan = clock.querySelector(".minutes");
        const secondsSpan = clock.querySelector(".seconds");

        function updateClock() {
          const t = getTimeRemaining(endtime);
          daysSpan.innerHTML = t.days;
          hoursSpan.innerHTML = ("0" + t.hours).slice(-2);
          minutesSpan.innerHTML = ("0" + t.minutes).slice(-2);
          secondsSpan.innerHTML = ("0" + t.seconds).slice(-2);

          if (t.total <= 0) {
            clearInterval(timeinterval);
          }
        }

        updateClock();
        const timeinterval = setInterval(updateClock, 10);
      }

      const deadline = new Date(
        Date.parse(new Date()) + 18 * 24 * 60 * 60 * 1000
      );
      initializeClock("clockdiv", deadline);
    
    },
    selectCalendar(event) {
      return this.event_data = event
    }
  },
  mounted: function() {
    this.countdownTime();
  },
};
</script>

<style scope>
h2 {
  color: #da694b;
  font-weight: 200;
}
.text-cal {
  color: #000000;
  font-weight: bold;
}
.text-span {
  color: #da694b;
  font-size: 28px;
  font-weight: initial;
}
#clockdiv {
  font-family: "Kanit";
  color: #fff;
  display: inline-block;
  font-weight: bold;
  text-align: center;
  font-size: 30px;
}

#clockdiv > div {
  padding: 10px;
  display: inline-block;
}

#clockdiv div > span {
  padding: 25px;
  border-radius: 12px;
  background: #000;
  display: inline-block;
}

.smalltext {
  padding-top: 5px;
  font-size: 16px;
  font-weight: bold;
  color: #254361;
}
</style>
