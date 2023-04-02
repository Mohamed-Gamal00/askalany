<template>
  <NavBarCom />
  <div class="container-fluid">
    <div
      class="row d-flex justify-content-center text-center my-4 py-5"
      style="background-color: #0c4da2"
    >
      <p class="fs-20 fw-bold text-orange">المقالات</p>
      <h3 class="fs-30 text-white" style="font-weight: 500">
        مركز العسقلاني المتخصص في طب الفم والأسنان
      </h3>
    </div>
  </div>
  <div class="articles">
    <div v-if="loading">
      <div>
        <PageLoader />
      </div>
    </div>
    <!-- اخر الاخبار -->
    <div class="container-fluid pt-lg-5">
      <div class="row d-flex justify-content-center">
        <div class="col-md-10">
          <div class="row">
            <div class="col-md-4" v-for="article in articles" :key="article">
              <router-link
                class="text-decoration-none"
                :to="{ name: 'article', params: { id: article.id } }"
              >
                <div class="card border-0" style="width: 100%">
                  <div
                    class="img_card"
                    style="
                      height: 300px;
                      background-color: black;
                      border-radius: 36px;
                    "
                  >
                    <img
                      :src="article.image"
                      class="card-img-top"
                      alt="img"
                      style="
                        height: 100%;
                        border-radius: 36px;
                        object-fit: cover;
                      "
                    />
                  </div>
                  <div
                    class="card-body text-center shadow"
                    style="
                      position: relative;
                      bottom: 65px;
                      background-color: white;
                      border-radius: 36px;
                      height: 227px;
                    "
                  >
                    <p class="card-text text-orange">
                      {{ article.date }}
                      <FontAwesome icon="clock" class="ms-2" />
                      13/11-2023
                    </p>
                    <h5 class="card-title text-black">{{ article.title }}</h5>
                    <p class="text-black">
                      هذا النص هو مثال لنص يمكن أن يستبدل في نفس المساحة، لقد تم
                      توليد هذا النص من
                    </p>
                    <router-link
                      class="m-2 border-0"
                      :to="{ name: 'article', params: { id: article.id } }"
                      exact
                    >
                      <span
                        style="background-color: #0c4da2"
                        class="btn fw-bold text-light rounded-pill border-2 py-3 px-4"
                      >
                        <FontAwesome icon="circle-arrow-left" class="ms-2" />
                        شاهد المزيد</span
                      >
                    </router-link>
                  </div>
                </div>
              </router-link>
            </div>
          </div>
          <br />
        </div>
      </div>
      <!-- pagination -->
      <div class="container mt-5">
        <div class="row mt-3 d-flex justify-content-center">
          <div class="col-md-10 d-flex justify-content-center">
            <nav aria-label="Page navigation example">
              <ul class="pagination p-0">
                <li
                  class="page-item"
                  v-for="link in pagination.links"
                  :key="link"
                  v-bind:class="[
                    { disabled: !link.url },
                    { active: link.active },
                  ]"
                >
                  <span
                    class="page-link"
                    v-html="link.label"
                    @click="fetcharticles(link.url)"
                  ></span>
                </li>
              </ul>
            </nav>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- تثبيت الفوتر لتحت -->
  <div style="position: relative; bottom: -55px; right: 0; left: 0">
    <FooterCom />
  </div>
</template>
<script>
import PageLoader from "@/components/pageloader/PageLoder.vue";

import axios from "axios";
import NavBarCom from "@/components/navbar/NavBar.vue";
import FooterCom from "@/components/footer/FooterCom.vue";
export default {
  name: "ArticlesCom",
  components: {
    PageLoader,
    NavBarCom,
    FooterCom,
  },
  data() {
    return {
      loading: false,

      // اخر الاخبار
      articles: [],
      pagination: {},
    };
  },
  async mounted() {
    this.fetcharticles();
  },
  methods: {
    async fetcharticles(page_url) {
      page_url = page_url || `https://admin.growth-tech.co/api/articles`;
      this.loading = true;
      let result = await axios
        .get(page_url)
        .catch(() => this.$router.push({ path: "/servererror" }));
      if (result.status == 200) {
        this.articles = result.data.data;
        console.log(this.articles);
        this.makePagination(result.data.meta);
      }
      this.loading = false;
    },

    async makePagination(meta) {
      let pagination = {
        links: meta.links,
      };
      this.pagination = pagination;
    },
  },
};
</script>
<style>
.articles {
  direction: rtl;
  color: #1f1e1e;
}
.shadow {
  box-shadow: 0 -0.5rem 1rem rgba(0, 0, 0, 0.15) !important;
}
</style>
