<template>
  <div class="calendar">
    <div id="todo-list">
      <h3>Midterm :</h3>
      <ul>
        <li v-for="mid in sort(midterm)" :key="mid">
          <!-- Style checkboxes -->
          <label class="container">
            <input
              type="checkbox"
              v-on:change="toggle(mid)"
              v-bind:checked="mid.completed"
            />
            <span class="checkmark"></span>
          </label>

          <!-- Completed task element -->
          <span class="completed" v-if="mid.completed">
            <p class="text-subj">{{ mid.item }}</p>
            <p class="text-date-time">{{ mid.date + " เวลา " + mid.time }}</p>
          </span>

          <span v-else>
            <p class="text-subj">{{ mid.item }}</p>
            <p class="text-date-time">{{ mid.date + " เวลา " + mid.time }}</p>
          </span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
//import $ from 'jquery'
export default {
  name: "midtermfinal",
  data: function() {
    return {
      midterm: [
        {
          item: "Human Computer Interaction and Interface Design",
          date: "24/01/564",
          time: "9:30-12:00",
          completed: false,
        },
        {
          item: "Household Environmental Management",
          date: "17/01/2564",
          time: "9:30-12:00",
          completed: false,
        },
      ],
    };
  },
  methods: {
    toggle: function(mid) {
      mid.completed = !mid.completed;
    },
    sort: function(arr) {
      return arr.slice().sort(function(a, b) {
        return a.date - b.date;
      });
    },
    // checkDate: function() {
    //     var chk = $(".todo-list");
    //     var date_d = new Date().getDate;
    //     var date_m = new Date().getMonth;
    //     var date_y = new Date().getFullYear;

    //     var str = $(el).find(".text-subj").text();
    // }
  },
  mounted: function() {},
};
</script>

<style scoped>
#todo-list {
  background: #df5c52;
  border-radius: 10px;
  padding: 30px;
  max-width: 400px;
  margin: 0 auto;
  transition: all 0.2s;
}

ul {
  background: #fff;
  padding: 50px;
  border-radius: 10px;
}

ul > li {
  list-style-type: none;
  margin-left: 20px;
}

.text-subj,
.text-date-time {
  font-size: 16px;
}

h3 {
  color: #fff;
  font-weight: bold;
  margin-bottom: 30px;
  text-align: center;
}

.container {
  display: block;
  position: relative;
  padding-left: 35px;
  margin-bottom: 12px;
  cursor: pointer;
  font-size: 22px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.container > input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}
.checkmark {
  position: absolute;
  top: -5px;
  left: -40px;
  height: 25px;
  width: 25px;
  border-radius: 50%;
  background-color: #eee;
}

.container:hover > input > .checkmark {
  background-color: #ccc;
}
.container:checked > .checkmark {
  background-color: #df5c52;
}
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

.container > input:checked > .checkmark:after {
  display: block;
}
.container > .checkmark:after {
  left: 9px;
  top: 5px;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 3px 3px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}

.completed {
  color: #df5c52;
  text-decoration: line-through;
}
</style>
