<template>
  <div>
    <!-- Start Nav Section -->
    <nav id="navbar" class="navbar">
      <ul class="nav-menu">
        <li>
          <a data-scroll="home" href="#home" class="dot active">
            <span>คำนวณหลักสูตร</span>
          </a>
        </li>
        <li>
          <a data-scroll="about" href="#about" class="dot">
            <span>แนะนำหากต้องการย้ายสาขา</span>
          </a>
        </li>
      </ul>
    </nav>
    <!-- End Nav Section -->

    <!-- Start Home Section -->
    <section id="home" class="section">
      <div class="container">
        <div class="content-wrapper text-center">
          <div class="content">
            <h1>Hello, I'm Ahmed Beheiry <br />Front-End Developer</h1>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit.
              Inventore odit ipsam expedita dolorem.<br />
              Distinctio, aliquid minima voluptatem saepe.
            </p>
            <a href="/subject_cal"><button>คำนวณหลักสูตร</button></a>
          </div>
        </div>
      </div>
    </section>
    <!-- Start About Me Section -->
    <section id="about">
      <div class="container">
        <div class="content-wrapper text-center">
          <div class="content">
            <h1>Hello, I'm Ahmed Beheiry <br />Front-End Developer</h1>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit.
              Inventore odit ipsam expedita dolorem.<br />
              Distinctio, aliquid minima voluptatem saepe.
            </p>
            <a href="/dataSubjectdiagram"><button>รายวิชาและตัวต่อ</button></a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
var $ = require("jquery");

export default {
    name: 'subjec_selected'
}

$(function() {
  var link = $("#navbar a.dot");

  // Move to specific section when click on menu link
  link.on("click", function(e) {
    var target = $($(this).attr("href"));
    $("html, body").animate(
      {
        scrollTop: target.offset().top,
      },
      600
    );
    $(this).addClass("active");
    e.preventDefault();
  });

  // Run the scrNav when scroll
  $(window).on("scroll", function() {
    scrNav();
  });

  // scrNav function
  // Change active dot according to the active section in the window
  function scrNav() {
    var sTop = $(window).scrollTop();
    $("section").each(function() {
      var id = $(this).attr("id"),
        offset = $(this).offset().top - 1,
        height = $(this).height();
      if (sTop >= offset && sTop < offset + height) {
        link.removeClass("active");
        $("#navbar")
          .find('[data-scroll="' + id + '"]')
          .addClass("active");
      }
    });
  }
  scrNav();
});
</script>


<style scoped>
* {
  box-sizing: border-box;
}
body {
  font-size: 14px;
  font-family: "Kanit", sans-serif;
  font-weight: 400;
  color: #333;
}
h1 {
    color: #2d3142;
}
p {
  color: #565656;
  line-height: 1.8;
}
.section {
  min-height: 800px;
}
.container {
  width: 1170px;
  max-width: 90%;
  margin: 0 auto;
}
.text-center {
  text-align: center;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.content-wrapper {
  width: 80%;
  margin: 0 auto;
  display: table;
  min-height: 800px;
}
.content {
  display: table-cell;
  width: 100%;
  vertical-align: middle;
}
/* End Global Styles */

/* Start Nav Styles */
.navbar {
  position: fixed;
  z-index: 999;
  top: 50%;
  right: 50px;
  transform: translateY(-50%);
}
.navbar .nav-menu {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
.navbar .nav-menu li {
  position: relative;
  min-width: 200px;
  text-align: right;
}
.navbar .nav-menu li .dot {
  display: block;
  color: #fff;
  padding: 5px 0;
}
.navbar .nav-menu li .dot::before,
.navbar .nav-menu li .dot::after {
  display: block;
  position: absolute;
  content: "";
  border-radius: 50%;
  top: 50%;
  transition: all 0.3s ease;
}
.navbar .nav-menu li .dot::before {
  width: 5px;
  height: 5px;
  right: 0;
  border: 2px solid #181818;
  transform: translateY(-50%);
}
.navbar .nav-menu li .dot::after {
  width: 15px;
  height: 15px;
  border: 2px solid #da694b;
  right: -5px;
  transform: translateY(-50%) scale(0);
}
.navbar .nav-menu li .dot.active::before,
.navbar .nav-menu li:hover .dot::before {
  background: #da694b;
  border-color: #da694b;
}
.navbar .nav-menu li .dot.active::after,
.navbar .nav-menu li:hover .dot::after {
  transform: translateY(-50%) scale(1);
}
.navbar .nav-menu li .dot span {
  display: inline-block;
  opacity: 0;
  font-weight: 700;
  letter-spacing: 0.5px;
  text-transform: capitalize;
  background-color: #da694b;
  padding: 10px 20px;
  border-radius: 3px;
  margin-right: 30px;
  transform: translateX(20px);
  transition: all 0.3s ease;
}
.navbar .nav-menu li .dot span::before {
  display: block;
  position: absolute;
  content: "";
  border-left: 7px solid #da694b;
  border-top: 7px solid transparent;
  border-bottom: 7px solid transparent;
  top: 50%;
  transform: translate(7px, -50%);
  right: 0;
  transition: all 0.3s ease;
}
.navbar .nav-menu li .dot.active span,
.navbar .nav-menu li:hover .dot span {
  transform: translateX(0px);
  opacity: 1;
}
/* End Nav Styles */

/* Start Home Styles */
#home {
  background-color: #eee;
}
#home button {
  border: 2px solid #4f5d75;
  background-color: transparent;
  outline: none;
  cursor: pointer;
  padding: 12px 25px;
  font-weight: 700;
  transition: all 0.3s ease;
  margin-top: 20px;
}
#home button:hover {
  background-color: #4f5d75;
  color: #fff;
}
/* End Home Styles */

/* Start About Styles */
#about {
  background-color: #f6f6f6;
}
#about button {
  border: 2px solid #4f5d75;
  background-color: transparent;
  outline: none;
  cursor: pointer;
  padding: 12px 25px;
  font-weight: 700;
  transition: all 0.3s ease;
  margin-top: 20px;
}
#about button:hover {
  background-color: #4f5d75;
  color: #fff;
}
/* End About Styles */
</style>