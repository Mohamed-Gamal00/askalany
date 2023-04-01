<template>
  <div class="Categories" style="direction: rtl">
    <!-- اجدد المشاريع -->
    <div class="container mt-5">
      <div v-if="loading">
        <div>
          <PageLoader />
        </div>
      </div>
      <!-- categories -->
      <div class="container">
        <div class="row d-flex justify-content-center">
          <div class="col-md-10">
            <div class="card" style="width: 18rem">
              <img
                src="@/assets/askalany/img.webp"
                class="card-img-top"
                alt="img"
              />
              <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <p class="card-text">
                  Some quick example text to build on the card title and make up
                  the bulk of the card's content.
                </p>
                <a href="#" class="btn btn-primary">Go somewhere</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import PageLoader from "@/components/pageloader/PageLoder.vue";
export default {
  name: "CategoriesCom",
  components: { PageLoader },
  data() {
    return {
      loading: false,
    };
  },
};
</script>

<style>
/* imag hover */
</style>
