<template>
  <NavBarCom />

  <div class="container-fluid">
    <section class="our-team-section">
      <div class="container">
        <div class="row">
          <div
            class="col-lg-3 col-md-6 col-sm-6 mt-4"
            v-for="member in members"
            :key="member"
          >
            <div class="our-team">
              <div class="pic" width="100" height="100">
                <img
                  src="@/assets/askalany/img.webp"
                  width="100"
                  height="100"
                  class="rounded-circle"
                />
              </div>
              <div class="team-content">
                <h3 class="title">{{ member.name }}</h3>
                <span class="post">{{ member.job }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
  <FooterCom />
</template>

<script>
import NavBarCom from "@/components/navbar/NavBar.vue";
import FooterCom from "@/components/footer/FooterCom.vue";
import axios from "axios";
export default {
  name: "SliderCom",
  components: { NavBarCom, FooterCom },
  data() {
    return {
      members: [],
    };
  },
  async mounted() {
    let result = await axios.get(`https://admin.growth-tech.co/api/team`);
    if (result.status == 200) {
      this.members = result.data.team;
      console.log(this.members);
    }
  },
};
</script>

<style>
.our-team-section {
  position: relative;
  padding-top: 40px;
  padding-bottom: 40px;
}
.our-team-section:before {
  position: absolute;
  top: -0;
  left: 0;
  content: " ";
  background-size: 100% 100px;
  width: 100%;
  height: 100px;
  float: left;
  z-index: 99;
}
.our-team {
  padding: 30px 0 40px;
  background: #f9f9f9;
  text-align: center;
  overflow: hidden;
  /* position: relative;
  border-bottom: 5px solid #ef4823; */
}
.our-team:hover {
  border-bottom: 5px solid #ef4823;
}

.our-team .pic {
  display: inline-block;
  width: 243px;
  height: 243px;
  margin-bottom: 50px;
  z-index: 1;
  position: relative;
}
.our-team .pic img {
  width: 100%;
  height: 243px;
  border-radius: 100%;
}
.our-team:hover .pic:before {
  height: 100%;
  background: #d3583c;
}
.our-team .pic:after {
  content: "";
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: #ef4823;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
  transition: all 0.3s linear 0s;
}
.our-team:hover .pic:after {
  background: #a73015;
}

.our-team .pic img {
  width: 100%;
  object-fit: cover;
  border-radius: 50%;
  transform: scale(1);
  transition: all 0.9s ease 0s;
  box-shadow: 0 0 0 14px #f7f5ec;
  transform: scale(0.7);
  position: relative;
  z-index: 2;
}
.our-team:hover .pic img {
  box-shadow: 0 0 0 14px #f7f5ec;
  transform: scale(0.7);
}
.our-team .team-content {
  margin-bottom: 30px;
}
.our-team .title {
  font-size: 22px;
  font-weight: 700;
  color: #4e5052;
  letter-spacing: 1px;
  text-transform: capitalize;
  margin-bottom: 5px;
}
.our-team .post {
  display: block;
  font-size: 15px;
  color: #4e5052;
  text-transform: capitalize;
}

@media only screen and (max-width: 990px) {
  .our-team {
    margin-bottom: 30px;
  }
}
</style>
