<template>
  <div class="home">
    <header>
      <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
        <ol class="carousel-indicators">
          <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
          <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
        </ol>
        <div class="carousel-inner" role="listbox">
          <div class="carousel-item active" style="background-image: url('https://scontent.fbkk8-4.fna.fbcdn.net/v/t1.0-9/144140726_3836410093082989_3475210957440590045_o.jpg?_nc_cat=100&ccb=2&_nc_sid=8bfeb9&_nc_eui2=AeHhdeiF6BJyUfH5AtiwPqbnMpwJkezySQMynAmR7PJJA64aaabtWfs_S1BCwXr9VYiBvdGjbhrj5dlf2Uw_KV5i&_nc_ohc=uG0quv_-CR8AX9fsvJP&_nc_ht=scontent.fbkk8-4.fna&oh=000b1064f4fc5886ff7851a2a3384681&oe=603FBD34')">
            <div class="carousel-caption d-none d-md-block">
              <h2 class="display-4" style="color: #fff">ยินดีตอนรับ!</h2>
              <p class="lead">ให้เราช่วยเหลือคุณในการลงทะเบียน</p>
            </div>
          </div>
          <div class="carousel-item" style="background-image: url('https://scontent.fbkk8-4.fna.fbcdn.net/v/t1.0-9/145135410_3836410369749628_8658527597412279472_o.jpg?_nc_cat=100&ccb=2&_nc_sid=8bfeb9&_nc_eui2=AeEuy-i9WVlwNnKL9DAyOq8b6X1Ow41TUuvpfU7DjVNS64F3WIwRR6PSpGW-J56ADMwUQXJ1qRU4oyO-2GwLexnb&_nc_ohc=kgX9Hx22o8oAX85HMdP&_nc_ht=scontent.fbkk8-4.fna&oh=400d8309611ff217b85f5fded947cc3b&oe=603CC458')">
            <div class="carousel-caption d-none d-md-block">
              <h2 class="display-4">Welcome!</h2>
              <p class="lead">Can I help you to Register.</p>
            </div>
          </div>
        </div>
        <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
              <span class="carousel-control-prev-icon" aria-hidden="true"></span>
              <span class="sr-only">Previous</span>
            </a>
        <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
              <span class="carousel-control-next-icon" aria-hidden="true"></span>
              <span class="sr-only">Next</span>
            </a>
      </div>
    </header>
    <!-- <aboutReg/>
    <themePublic/> -->
    <h2 class="cal">ปฏิทินนักศึกษา</h2>
    <CalendarHome/>
    <NewsEvent/>
  </div>
</template>

<script>
// @ is an alias to /src
import CalendarHome from '../components/CalendarHome.vue'
import NewsEvent from '../components/NewsEvent.vue'

export default {
  name: 'Home',
  components: {
    CalendarHome,
    NewsEvent
  }
}
</script>
<style scoped>
  h2.cal {
  color: #254361;
  font-weight: bold;
  padding-top: 32px;
  padding-bottom: 26px;
}
.carousel-item {
  height: 93vh;
  min-height: 350px;
  background: no-repeat center center scroll;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
</style>
