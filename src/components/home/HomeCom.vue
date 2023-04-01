<template>
  <NavBarCom />
  <div v-if="loading">
    <div>
      <PageLoader />
    </div>
  </div>
  <div class="home mt-4" style="direction: rtl" id="home">
    <!-- text and image -->
    <div class="container">
      <div class="row d-flex justify-content-center">
        <div class="col-md-10">
          <div class="row align-items-center justify-content-between mb-2">
            <div class="col-lg-5 fw-bold align-middle text-center text-lg-end">
              <h2
                class="mb-4 font_h1 fw-bold"
                style="font-weight: 900 !important"
              >
                مركز العسقلاني
              </h2>
              <p class="pb-3 font_p_home" style="color: #1f1e1e">
                مركز العسقلاني لطب الأسنان
              </p>
              <p class="pb-3 font_p_home" style="color: #1f1e1e">
                احصل علي ابستامه مشرقة وصحية بمركز العسقلاني لطب الاسنان, معالجة
                الأسنان ب احدث التقنيات, تخلص من مشاكل الاسنان.
              </p>
              <a
                href="#contact_us"
                aria-label="contact"
                style="background-color: #f48928"
                class="btn fw-bold mb-4 text-light rounded-pill border-2 py-3 px-4"
              >
                <FontAwesome icon="circle-arrow-left" class="ms-2" />
                احجز موعد</a
              >
            </div>
            <div class="col-lg-6 text-center mt-sm-4 text-lg-start">
              <img
                class="img-fluid rounded-3"
                src="@/assets/askalany/img.webp"
                alt="img"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- counter -->
    <div
      data-aos="fade-up"
      data-aos-easing="ease-out-cubic"
      data-aos-duration="1500"
      class="container-fluid mt-lg-5 pt-lg-5"
      style="background-color: #f8faff"
    >
      <div class="container">
        <!-- text image -->
        <div class="row d-flex justify-content-center">
          <div class="col-md-10">
            <div class="row align-items-center justify-content-between mb-2">
              <div class="col-lg-6 text-center mt-sm-4">
                <img
                  class="img-fluid rounded-3"
                  src="@/assets/askalany/webp.webp"
                  width="388"
                  height="317"
                  alt="img"
                />
              </div>
              <div
                class="col-lg-5 fw-bold align-middle text-center text-lg-end"
              >
                <h2
                  class="mb-4 font_h1 fw-bold"
                  style="font-weight: 900 !important"
                >
                  مركز العسقلاني
                </h2>
                <p class="pb-3 font_p_home" style="color: #1f1e1e">
                  مركز العسقلاني لطب الأسنان
                </p>
                <p class="pb-3 font_p_home" style="color: #1f1e1e">
                  احصل علي ابستامه مشرقة وصحية بمركز العسقلاني لطب الاسنان,
                  معالجة الأسنان ب احدث التقنيات, تخلص من مشاكل الاسنان.
                </p>
                <a
                  href="#contact_us"
                  aria-label="contact"
                  style="background-color: #f48928"
                  class="btn fw-bold mb-4 text-light rounded-pill border-2 py-3 px-4"
                >
                  <FontAwesome icon="circle-arrow-left" class="ms-2" />
                  احجز موعد</a
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- section 3 -->
    <section class="py-5">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-md-10">
            <div class="row justify-content-center text-center">
              <div class="col-md-4" v-for="card in cards" :key="card.id">
                <div class="text-center position-relative">
                  <div
                    class="mx-auto rounded-4 d-flex align-items-center justify-content-center"
                    style="
                      width: 70px;
                      height: 70px;
                      border-radius: 16px;
                      background-color: #fde7d4;
                      color: #f48928;
                    "
                  >
                    <FontAwesome :icon="card.icon" />
                  </div>
                  <p class="fs-18 mt-3">
                    {{ card.title }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- section 4 worktime-->
    <section class="py-5">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-md-10">
            <div class="row justify-content-center text-center">
              <div>
                <h3 class="fw-bold fs-20">مواعيد العمل</h3>
                <p class="fs-30 fw-bold">
                  تعرف علي مواعيد العمل والخدمات المتاحة
                </p>
                <p class="fs-14 mb-0">
                  من الساعة 12 ظهرا حتى الساعة 11 مساءا (بحجز مسبق)
                </p>
                <p class="fs-14">
                  الجمعة: من الساعة 4 مساءا حتى الساعة 9 مساءا (بحجز مسبق)
                </p>
              </div>
            </div>
            <div class="row justify-content-center text-center">
              <WorkTime />
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- work -->
    <!-- الشركاء -->
    <div class="container">
      <div class="row d-flex justify-content-center">
        <div class="col-md-10">
          <PrtnersCom />
        </div>
      </div>
    </div>
  </div>

  <!-- تواصل معنا -->
  <div class="container-fluid mt-5" style="background-color: #f8faff">
    <!-- text -->
    <div class="container">
      <div class="row d-flex justify-content-center">
        <div class="col-md-10">
          <h1
            class="text-end fw-bold background"
            data-aos="fade-up"
            data-aos-easing="ease-out-cubic"
            data-aos-duration="600"
            data-aos-once="false"
          >
            <strong>تواصل معنا</strong>
          </h1>
          <p
            class="fw-bold lh-lg"
            data-aos="zoom-in"
            data-aos-easing="ease-out-cubic"
            data-aos-duration="600"
            data-aos-delay="100"
            data-aos-once="false"
          >
            نسعد بتواصلكم معنا دائمًا، ونحرص على تقديم إجابات سريعة لكل
            الاستفسارات والتساؤلات الهامة.
          </p>
        </div>
      </div>
    </div>
    <!-- تواصل معنا -->
    <div class="row d-flex justify-content-center" id="contact_us">
      <div class="col-md-10">
        <div class="row">
          <section class="mt-5">
            <div class="container h-100">
              <div
                class="row d-flex justify-content-center align-items-center h-50"
              >
                <div class="col-lg-12 col-xl-11">
                  <div class="card text-black border-0">
                    <div
                      class="card-body p-0"
                      style="direction: ltr; background-color: #f8faff"
                    >
                      <div class="row justify-content-center">
                        <div
                          class="col-md-10 col-lg-6 col-xl-6 order-2 order-lg-1"
                        >
                          <form class="mx-1 mx-md-4" style="direction: rtl">
                            <div class="row">
                              <div class="col-md-6">
                                <!--  الاسم -->
                                <div
                                  class="d-flex flex-row align-items-center mb-4"
                                >
                                  <div class="form-outline flex-fill mb-0">
                                    <label
                                      class="form-label"
                                      for="form3Example1c"
                                      >الاسم</label
                                    >
                                    <input
                                      type="text"
                                      id="form3Example1c"
                                      class="form-control border-top-0 border-start-0 border-end-0"
                                      v-model="contact.name"
                                    />
                                    <span
                                      class="erroe-feedbak"
                                      v-if="v$.contact.name.$error"
                                      >{{
                                        v$.contact.name.$errors[0].$message
                                      }}</span
                                    >
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-6">
                                <!-- رقم الهاتف -->
                                <div
                                  class="d-flex flex-row align-items-center mb-4"
                                >
                                  <div class="form-outline flex-fill mb-0">
                                    <label
                                      class="form-label"
                                      for="form3Example3c"
                                      >رقم الهاتف</label
                                    >
                                    <input
                                      type="number"
                                      id="form3Example3c"
                                      class="form-control border-top-0 border-start-0 border-end-0"
                                      v-model="contact.number"
                                    />
                                    <span
                                      class="erroe-feedbak"
                                      v-if="v$.contact.number.$error"
                                      >{{
                                        v$.contact.number.$errors[0].$message
                                      }}</span
                                    >
                                  </div>
                                </div>
                              </div>
                            </div>
                            <!-- البريد الالكتروني -->
                            <div
                              class="d-flex flex-row align-items-center mb-4"
                            >
                              <div class="form-outline flex-fill mb-0">
                                <label class="form-label" for="form3Example4c"
                                  >البريد الالكتروني</label
                                >
                                <input
                                  type="email"
                                  id="form3Example4c"
                                  class="form-control border-top-0 border-start-0 border-end-0"
                                  v-model="contact.email"
                                />
                                <span
                                  class="erroe-feedbak"
                                  v-if="v$.contact.email.$error"
                                  >{{
                                    v$.contact.email.$errors[0].$message
                                  }}</span
                                >
                              </div>
                            </div>
                            <!--  الموضوع -->
                            <div
                              class="d-flex flex-row align-items-center mb-4"
                            >
                              <div class="form-outline flex-fill mb-0">
                                <label class="form-label" for="form4Example1c"
                                  >الموضوع</label
                                >
                                <input
                                  type="text"
                                  id="form4Example1c"
                                  class="form-control border-top-0 border-start-0 border-end-0"
                                  v-model="contact.subject"
                                />
                                <span
                                  class="erroe-feedbak"
                                  v-if="v$.contact.subject.$error"
                                  >{{
                                    v$.contact.subject.$errors[0].$message
                                  }}</span
                                >
                              </div>
                            </div>
                            <!-- الرسالة -->
                            <div
                              class="d-flex flex-row align-items-center mb-4"
                            >
                              <div class="form-outline" style="width: 100%">
                                <label class="form-label" for="textAreaExample"
                                  >الرسالة</label
                                >
                                <textarea
                                  class="form-control"
                                  id="textAreaExample1"
                                  rows="4"
                                  v-model="contact.message"
                                ></textarea>
                                <span
                                  class="erroe-feedbak"
                                  v-if="v$.contact.message.$error"
                                  >{{
                                    v$.contact.message.$errors[0].$message
                                  }}</span
                                >
                              </div>
                            </div>
                            <!-- ارسال -->
                            <div class="text-start mb-3 mt-4 mb-lg-4">
                              <button
                                style="background-color: #f48928; border: none"
                                @click="contactus()"
                                type="button"
                                class="btn btn-primary btn-lg text-end"
                              >
                                ارسال
                              </button>
                            </div>
                          </form>
                        </div>
                        <div
                          class="col-md-10 col-lg-6 col-xl-6 d-flex align-items-center order-1 order-lg-2"
                        >
                          <img
                            src="@/assets/new_img/webp/contact_us.webp"
                            class="img-fluid"
                            height="400"
                            alt="Sample"
                          />
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>
        </div>
      </div>
    </div>
  </div>
  <FooterCom />
</template>

<script>
import PageLoader from "@/components/pageloader/PageLoder.vue";
import WorkTime from "@/components/home/WorkTime.vue";
import axios from "axios";
import useValidate from "@vuelidate/core";
import { required, email } from "@vuelidate/validators";
import NavBarCom from "@/components/navbar/NavBar.vue";
import PrtnersCom from "@/components/slider/PartnersCom.vue";
import FooterCom from "@/components/footer/FooterCom.vue";
export default {
  name: "HomeCom",
  components: {
    NavBarCom,
    WorkTime,
    FooterCom,
    PrtnersCom,
    PageLoader,
  },
  data() {
    return {
      loading: false,
      cards: [
        {
          title: "جودة وكفاة من فريق الأطباء للوصول الي اعلى درجات الرضى.",
          icon: "circle-check",
        },
        {
          title:
            "فريق كامل من الأطباء والممرضين للوصول بالخدمة الي اعلى مستوى.",
          icon: "users",
        },
        {
          title: "اطباء علي اعلى مستوى من الكفاءه.",
          icon: "chart-simple",
        },
      ],
      isOpen: false,
      v$: useValidate(),
      contact: {
        name: "",
        number: "",
        email: "",
        subject: "",
        message: "",
      },
    };
  },
  validations() {
    return {
      contact: {
        name: { required },
        number: { required },
        email: { required, email },
        subject: { required },
        message: { required },
      },
    };
  },
  async mounted() {
    this.loading = true;
    this.loading = false;
  },
  methods: {
    async contactus() {
      this.loading = true;
      this.v$.$validate();
      if (!this.v$.$error) {
        let result = await axios.post(
          `https://admin.growth-tech.co/api/contact`,
          this.contact
        );
        if (result.status == 200) {
          this.$swal.fire({
            icon: "success",
            title: "تم...",
            text: "عملية تسجيل ناجحة",
            footer: "<p>تم تسجيل ردك بنجاح</p>",
            timer: 2000,
          });
          setTimeout(() => {
            this.successMessage = "";
            this.contact.name = "";
            this.contact.number = "";
            this.contact.email = "";
            this.contact.subject = "";
            this.contact.message = "";
            (this.v$.contact.name.$errors[0].$message = ""),
              (this.v$.contact.number.$errors[0].$message = ""),
              (this.v$.contact.email.$errors[0].$message = ""),
              (this.v$.contact.subject.$errors[0].$message = ""),
              (this.v$.contact.message.$errors[0].$message = "");
          }, 2000);
        }
      } else {
        this.$swal.fire({
          icon: "error",
          title: "Oops...",
          text: "عملية تسجيل خاطئة",
          footer: "<p>املئ البيانات بطريقة صحيحة</p>",
          timer: 2000,
        });
      }
      this.loading = false;
    },
  },
};
</script>

<style>
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

input[type="number"] {
}
.home {
  direction: rtl;
  color: #1f1e1e !important;
}
</style>
