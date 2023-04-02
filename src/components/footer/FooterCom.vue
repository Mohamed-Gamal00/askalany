<template>
  <div
    class="container-fluid mt-5"
    style="background-color: #ffffff; direction: rtl"
  >
    <div class="row d-flex justify-content-center">
      <div class="col-md-9">
        <div class="row">
          <footer>
            <!-- Footer Start -->
            <div class="text-light" style="margin-top: 6rem">
              <div class="container py-5">
                <div class="row g-5">
                  <!--Growth-->
                  <div class="col-md-6 col-lg-4 text-center p-0">
                    <span class="">
                      <img
                        src="@/assets/askalany/logo.jpg"
                        style="position: relative; bottom: 30px"
                        width="100"
                        alt="img"
                      />
                    </span>
                    <p class="text-black">
                      فريق كامل من أفضل الأطباء وفي كل المجالات التي تخدم مجال
                      طب جراحة الفم والأسنان, متخصصون في زراعة الأسنان, التقويم,
                      تجميل الأسنان.
                    </p>
                    <div class="d-flex justify-content-center pt-2">
                      <a
                        class="btnn btn-outline-light btn-social"
                        target="_blank"
                        aria-label="facebook"
                        href="#"
                        ><FontAwesome :icon="['fab', 'facebook']"
                      /></a>
                      <a
                        class="btnn btn-outline-light btn-social"
                        target="_blank"
                        aria-label="Twitter"
                        href="#"
                        ><FontAwesome :icon="['fab', 'twitter']"
                      /></a>
                      <a
                        class="btnn btn-outline-light btn-social"
                        target="_blank"
                        aria-label="instagram"
                        href="#"
                        ><FontAwesome :icon="['fab', 'instagram']"
                      /></a>
                      <a
                        class="btnn btn-outline-light btn-social"
                        target="_blank"
                        aria-label="linkedin"
                        href="#"
                        ><FontAwesome :icon="['fab', 'youtube']"
                      /></a>
                    </div>
                  </div>
                  <!-- الشركة -->
                  <div class="col-md-6 col-lg-3">
                    <h5 class="text-black text-center mb-4">اقسام الموقع</h5>
                    <router-link
                      class="btn_btn_link text-decoration-none"
                      :to="{ name: 'home' }"
                      >الرئيسية</router-link
                    >
                    <router-link
                      class="btn_btn_link text-decoration-none my-3"
                      :to="{ name: 'about' }"
                      >من نحن</router-link
                    >
                    <router-link
                      class="btn_btn_link text-decoration-none my-3"
                      :to="{ name: 'services' }"
                      >الخدمات</router-link
                    >
                    <router-link
                      class="btn_btn_link text-decoration-none my-3"
                      :to="{ name: 'join' }"
                      >انضم الينا</router-link
                    >
                    <router-link
                      class="btn_btn_link text-decoration-none my-3"
                      :to="{ name: 'articles' }"
                      >المدونة</router-link
                    >
                  </div>
                  <!-- العمل -->
                  <div class="col-md-6 col-lg-5">
                    <h5 class="text-black text-center mb-4">تواصل معنا</h5>
                    <div>
                      <div class="card rounded-5" style="width: 100%">
                        <div class="card-body text-black">
                          <h5 class="card-title fs-16 fw-bold">
                            <FontAwesome
                              class="ms-2 bg-orange"
                              icon="location-dot"
                            />العنوان
                          </h5>
                          <p class="card-text fs-14 p-0">
                            المنصورة - بجوار مصرللطيران - خلف بنك الإسكان و
                            التعمير
                          </p>
                          <h5 class="card-title fs-16 fw-bold">
                            <FontAwesome class="ms-2 bg-orange" icon="phone" />
                            الهاتف
                          </h5>
                          <p class="card-text fs-14">
                            01030722206 - 0502337738 - 0502333738
                          </p>
                        </div>
                      </div>
                    </div>
                    <div class="card rounded-5 mt-2" style="width: 100%">
                      <div class="card-body text-black">
                        <h5 class="card-title fs-16 fw-bold">
                          <FontAwesome
                            class="ms-2 bg-orange"
                            icon="location-dot"
                          />العنوان
                        </h5>
                        <p class="card-text fs-14 p-0">
                          منية النصر - مقابل المستشفي العام - خلف المطافي
                        </p>
                        <h5 class="card-title fs-16 fw-bold">
                          <FontAwesome class="ms-2 bg-orange" icon="phone" />
                          الهاتف
                        </h5>
                        <p class="card-text fs-14">01006789317 - 0503584161</p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="container">
                <div class="row">
                  <div class="col-md-12 text-black text-center mb-3 mb-md-0">
                    All Right Reserved. Designed By &copy;
                    <a
                      class="border-bottom text-decoration-none"
                      style="color: #f48928 !important"
                      >SIGMA</a
                    >
                  </div>
                </div>
              </div>
            </div>
            <!-- Footer End -->
          </footer>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FooterCom",
};
</script>

<style scoped>
a {
  color: rgb(0, 0, 0) !important;
}
:root {
  --primary: #2380be;
  --light: #05121b;
  --dark: #0e2e50;
}
.btnn.btn-social {
  margin-right: 5px;
  width: 40px;
  height: 40px;
  border-radius: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #f48928;
  color: var(--light);
  border: 1px solid rgba(256, 256, 256, 0.1);
  transition: 0.3s;
}

.btnn.btn-social:hover {
  color: var(--primary);
}

.btn_btn_link {
  display: block;
  margin-bottom: 10px;
  padding: 0;
  text-align: center;
  color: var(--light);
  font-weight: normal;
  transition: 0.3s;
  color: black;
}
.btn_btn_link:hover {
  letter-spacing: 0.5px;
  box-shadow: none;
  color: #0099ff;
}

.btn_btn_link::before {
  position: relative;
  content: "";
  font-family: "Font Awesome 5 Free";
  font-weight: 900;
  margin-right: 10px;
}
</style>
