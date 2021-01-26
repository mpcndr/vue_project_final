<template>
  <div class="container">
    <div class="row profile">
      <div class="col-md-3">
        <div class="profile-sidebar">
          <!-- SIDEBAR USERPIC -->
          <div class="profile-userpic">
            <img
              src="../assets/8c048ebaf3b009ffd259a43661145b21.jpg"
              class="img-responsive"
              alt=""
            />
          </div>
          <!-- END SIDEBAR USERPIC -->
          <!-- SIDEBAR USER TITLE -->
          <div class="profile-usertitle">
            <h2 class="profile-name">
              ชนัฐฎา รูปงาม
            </h2>
            <h5 class="profile-faculty">
              คณะวิทยาศาสตร์<br>
              <small>วิทยาการคอมพิวเตอร์</small>
            </h5>
          </div>
          <!-- END SIDEBAR USER TITLE -->
          <!-- SIDEBAR BUTTONS -->
          <div
            class="nav flex-column nav-pills"
            id="v-pills-tab"
            role="tablist"
            aria-orientation="vertical"
            style="padding-top: 18px"
          >
            <a
              class="menu-item active"
              id="v-pills-home-tab"
              data-toggle="pill"
              href="#v-pills-home"
              role="tab"
              aria-controls="v-pills-home"
              aria-selected="true"
              >
              <i class="fa fa-address-card-o" aria-hidden="true"></i>
              <span>ประวัตินักศึกษา</span></a
            >
            <a
              class="menu-item"
              id="v-pills-profile-tab"
              data-toggle="pill"
              href="#v-pills-profile"
              role="tab"
              aria-controls="v-pills-profile"
              aria-selected="false"
              ><i class="fa fa-graduation-cap" aria-hidden="true"></i
              ><span>ผลการเรียน</span></a
            >
            <a
              class="menu-item"
              id="v-pills-messages-tab"
              data-toggle="pill"
              href="#v-pills-messages"
              role="tab"
              aria-controls="v-pills-messages"
              aria-selected="false"
              ><i class="fa fa-table" aria-hidden="true"></i
              ><span>ตารางเรียน</span></a
            >
            <a
              class="menu-item"
              id="v-pills-settings-tab"
              data-toggle="pill"
              href="#v-pills-settings"
              role="tab"
              aria-controls="v-pills-settings"
              aria-selected="false"
              ><i class="fa fa-file-text-o" aria-hidden="true"></i
              ><span>ตารางสอบ</span></a
            >
          </div>
          <!-- END MENU -->
        </div>
      </div>
      <div class="col-md-9">
        <div class="tab-content" id="v-pills-tabContent">
          <ProfileData
            class="tab-pane fade show active"
            id="v-pills-home"
            role="tabpanel"
            aria-labelledby="v-pills-home-tab"
          >
          </ProfileData>
          <StudyResult
            class="tab-pane fade"
            id="v-pills-profile"
            role="tabpanel"
            aria-labelledby="v-pills-profile-tab"
          >
          </StudyResult>
          <div
            class="tab-pane fade"
            id="v-pills-messages"
            role="tabpanel"
            aria-labelledby="v-pills-messages-tab"
          >
            ...3
          </div>
          <MidtermFinal
            class="tab-pane fade"
            id="v-pills-settings"
            role="tabpanel"
            aria-labelledby="v-pills-settings-tab"
          >
            ...4
          </MidtermFinal>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProfileData from "../components/Profile_data.vue";
import StudyResult from "../components/StudyResult.vue";
import MidtermFinal from "../components/CalendarEvents.vue"

export default {
  name: "profile_user",
  components: {
    ProfileData,
    StudyResult,
    MidtermFinal,
  },
  methods: {
  },
};
</script>

<style scoped>
/***
User Profile Sidebar by @keenthemes
A component of Metronic Theme - #1 Selling Bootstrap 3 Admin Theme in Themeforest: https://j.mp/metronictheme
Licensed under MIT
***/

/* Profile container */
.profile {
  margin: 20px 0;
}

/* Profile sidebar */
.profile-sidebar {
  padding: 20px 0 10px 0;
  background: #fff;
}

.profile-userpic img {
  float: none;
  margin: 0 auto;
  width: 75%;
  height: 75%;
  -webkit-border-radius: 50% !important;
  -moz-border-radius: 50% !important;
  border-radius: 50% !important;
}

.profile-usertitle {
  text-align: center;
  margin-top: 20px;
  size: 30px;
}

.profile-usertitle-name {
  color: #5a7391;
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 7px;
}

/* Profile Content */
.profile-content {
  padding: 20px;
  background: rgb(230, 229, 229);
  min-height: 460px;
}

div.profile-usermenu {
  display: block;
  padding-top: 20px;
}

a.menu-item {
  color: #5a7391;
  text-decoration: none;
  padding-top: 10px;
  font-size: 18px;
}
a.menu-item:hover {
  color: #26384e;
}
a.menu-item:focus {
  color: #26384e;
}
i.fa {
  padding-right: 6px;
}
div.menu {
  padding-bottom: 8px;
}
</style>
