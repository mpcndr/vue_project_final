<template>
  <div class="container">
    <div class="con2">
      <img class="logo-su" src="../assets/logo_circle_eng_big.png" style="" />
      <div class="form-top">
        <i class="fas fa-user"></i>
        <input type="text" placeholder="username" class="" />
      </div>
      <div class="form-bottom">
        <i class="fa fa-unlock-alt" aria-hidden="true"></i>
        <input type="password" placeholder="password" />
      </div>
      <button class="login-btn">เข้าสู่ระบบ</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "login",
};
</script>
<style scoped>
i {
  margin-right: 10px;
}
input {
  margin-bottom: 12px;
}
.form-top {
  margin-top: 25px;
}
img.logo-su {
  width: 160px;
  heigth: 160px;
  margin-top: 25px;
}
.login-btn {
  background-color: #00766a; /* Green */
  border: none;
  border-radius: 10px;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 14px;
  transition-duration: 0.4s;
  outline-style: none;
}
.login-btn:hover {
  background-color: #fff;
  border-style: solid;
  color: #00766a;
  box-shadow: 0 12px 16px 0 rgba(0, 0, 0, 0.24),
    0 14px 30px 0 rgba(0, 0, 0, 0.19);
}
.container {
  position: relative;
}
.con2 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, 50%);
}
</style>
