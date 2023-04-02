<template>
  <NavBarCom />
  <div class="container-fluid">
    <div
      class="row d-flex justify-content-center text-center my-4 py-5"
      style="background-color: #0c4da2"
    >
      <p class="fs-20 fw-bold text-orange">انضم الينا</p>
      <h3 class="fs-30 text-white" style="font-weight: 500">
        انضم لفريق عمل مركز العسقلاني لطب الفم والأسنان
      </h3>
    </div>
  </div>
  <!-- تواصل معنا -->
  <div class="container-fluid mt-5">
    <div class="row d-flex justify-content-center">
      <div class="col-md-10">
        <div class="row">
          <section class="mt-5">
            <div class="container h-100">
              <div
                class="row d-flex justify-content-center align-items-center h-50"
              >
                <div class="col-lg-12 col-xl-11">
                  <div class="card text-black border-0">
                    <div class="card-body p-0" style="direction: ltr">
                      <div class="row justify-content-center">
                        <div
                          class="col-md-10 col-lg-6 col-xl-6 order-2 order-lg-1"
                        >
                          <form
                            class="mx-1 mx-md-4 input-icons"
                            style="direction: rtl"
                          >
                            <div class="row">
                              <div class="col-md-12">
                                <!--  الاسم الاول -->
                                <div
                                  class="d-flex flex-row align-items-center mb-4"
                                >
                                  <div class="form-outline flex-fill mb-0">
                                    <FontAwesome icon="user" class="icon" />

                                    <input
                                      type="text"
                                      placeholder="الاسم الاول"
                                      class="form-control"
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
                              <div class="col-md-12">
                                <!--  الاسم الثانس -->
                                <div
                                  class="d-flex flex-row align-items-center mb-4"
                                >
                                  <div class="form-outline flex-fill mb-0">
                                    <FontAwesome icon="user" class="icon" />
                                    <input
                                      type="text"
                                      placeholder="الاسم الاخير"
                                      class="form-control"
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
                              <div class="col-md-12">
                                <!-- رقم الهاتف -->
                                <div
                                  class="d-flex flex-row align-items-center mb-4"
                                >
                                  <div class="form-outline flex-fill mb-0">
                                    <FontAwesome icon="phone" class="icon" />
                                    <input
                                      type="number"
                                      placeholder="رقم الهاتف"
                                      class="form-control"
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
                                <FontAwesome icon="envelope" class="icon" />
                                <input
                                  type="email"
                                  placeholder="البريد الالكتروني"
                                  class="form-control"
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
                                <select
                                  class="form-select"
                                  aria-label="Default select example"
                                >
                                  <option>انضم ك</option>
                                  <option value="1">One</option>
                                  <option value="2">Two</option>
                                </select>
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
                            src="@/assets/askalany/join.jpg"
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
import axios from "axios";
import useValidate from "@vuelidate/core";
import { required, email } from "@vuelidate/validators";
import NavBarCom from "@/components/navbar/NavBar.vue";
import FooterCom from "@/components/footer/FooterCom.vue";
export default {
  name: "HomeCom",
  components: {
    NavBarCom,
    FooterCom,
  },
  data() {
    return {
      loading: false,
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

<style scoped>
.form-control[data-v-33d61464],
.form-select[data-v-33d61464] {
  border-radius: 20px !important;
  padding: 7px 28px !important;
}
.form-select:focus {
  color: #212529;
  background-color: #fff;
  border-color: #f48928 !important;
  outline: 0;
  box-shadow: 0 0 0 0.25rem #ff861857 !important;
}
.form-control,
.form-select {
  border-radius: 20px;
}
.form-control:focus {
  color: #212529;
  background-color: #fff;
  border-color: #f48928 !important;
  outline: 0;
  box-shadow: 0 0 0 0.25rem #ff861857 !important;
}
::placeholder {
  color: #f48928 !important;
  font-size: 14px;
}
.icon {
  position: relative !important;
  top: 32px !important;
  right: 10px !important;
  color: #f48928 !important;
}
</style>
