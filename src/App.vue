<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg bg-light">
      <div class="container">
        <a class="navbar-brand" id="logo-text">regGuide</a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarResponsive"
          aria-expanded="false"
          aria-label="Toggle navigation"
          aria-controls="#navbarResponsive"
        >
          <a id="icon-menu" href="javascript:void(0)" aria-hidden="true"
            ><i class="fa fa-bars" aria-hidden="true"></i
          ></a>
        </button>
        <div class="collapse navbar-collapse" id="navbarResponsive">
          <ul id="ul-underline" class="navbar-nav ml-auto">
            <router-link to="/" id="text-underline" class="nav-link active"
              >หน้าแรก</router-link
            >
            <router-link
              to="/about_subject"
              id="text-underline"
              class="nav-link"
              >วิชาเลือก</router-link
            >
            <router-link
              to="/subject_selected"
              id="text-underline"
              class="nav-link"
              >หลักสูตร</router-link
            >
            <!-- <span v-if="IsLoggedIn">
              <a @click="logout">ออกจากระบบ</a>
            </span>
            <span v-else>
              
            </span> -->
            <!-- <router-link to="/login" id="text-underline" class="nav-link">เข้าสู่ระบบ</router-link> -->
            <!-- <button
              type="button"
              class="btn btn-danger"
              data-mdb-toggle="modal"
              data-mdb-target="#login_id"
            >
            <router-link to="/profile" style="text-decoration: none; color: #fff">เข้าสู่ระบบ</router-link>
              
            </button> -->

            <div class="dropdown show">
              <a
                class="btn btn-danger dropdown-toggle"
                href="#"
                role="button"
                id="dropdownMenuLink"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
              >
                ชนัฐฎา รูปงาม
              </a>

              <div class="dropdown-menu" aria-labelledby="dropdownMenuLink">
                <a class="dropdown-item"><router-link to="/profile" style="text-decoration: none; color: #000">ข้อมูลส่วนตัว</router-link></a>
                <a class="dropdown-item"><router-link to="/profile" style="text-decoration: none; color: #000">ออกจากระบบ</router-link></a>
              </div>
            </div>
          </ul>
        </div>
      </div>
    </nav>
    <a
      id="back-to-top"
      href="#"
      class="btn btn-dark btn-lg back-to-top"
      role="button"
      ><i class="fa fa-arrow-up justify-content-center" aria-hidden="true"></i
    ></a>
    <router-view />
  </div>
</template>

<script>
var $ = require("jquery");

$(document).ready(function() {
  $(window).scroll(function() {
    if ($(this).scrollTop() > 50) {
      $("#back-to-top").fadeIn();
    } else {
      $("#back-to-top").fadeOut();
    }
  });
  // scroll body to 0px on click
  $("#back-to-top").click(function() {
    $("body,html").animate(
      {
        scrollTop: 0,
      },
      100
    );
    return false;
  });
});

export default {};
</script>

<style>
#app {
  font-family: "Kanit";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#logo-text {
  font-size: 26px;
  font-weight: bold;
  color: #da694b;
}
.navbar {
  padding-left: 0px;
}

#text-underline {
  font-size: 16px;
  color: rgb(133, 133, 133);
  margin: 0 15px;
  letter-spacing: 2px;
  text-transform: uppercase;
  text-decoration: none;

  display: inline-block;
  position: relative;
  /* font-weight: bold; */
}
#text-underline:after {
  background: none repeat scroll 0 0 transparent;
  bottom: -2;
  content: "";
  display: block;
  height: 2px;
  left: 50%;
  position: absolute;
  background: #da694b;
  transition: width 0.3s ease 0s, left 0.3s ease 0s;
  width: 0;
}
#text-underline:hover:after {
  width: 60%;
  left: 18%;
}
@media screen and (max-height: 300px) {
  ul {
    margin-top: 40px;
  }
}

li > a#text-underline:hover {
  color: #da694b;
}
a#text-underline.text-icon {
  font-size: 20px;
}

#ul-underline {
  margin: 0px 0px 0;
  padding: 0;
  list-style: none;
  display: flex;
  text-align: center;
}
li.nav-item {
  display: table-cell;
  position: relative;
}

a#icon-menu {
  text-decoration: none;
  display: inline-block;
  color: #da694b;
}

a#icon-menu:hover {
  text-decoration: underline;
  color: #e28d76;
}

.back-to-top {
  width: 70px;
  height: 47px;
  position: fixed;
  bottom: 25px;
  right: 25px;
  display: none;
}
</style>
