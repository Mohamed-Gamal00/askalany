<template>
  <NavBarCom />
  <h1>خدمتنا</h1>
  <FooterCom />
</template>
<script>
import NavBarCom from "@/components/navbar/NavBar.vue";
import FooterCom from "@/components/footer/FooterCom.vue";
export default {
  name: "ServicesCom",
  components: {
    NavBarCom,
    FooterCom,
  },
  data() {
    return {
      services: [
        { id: 1 },
        { id: 2 },
        { id: 3 },
        { id: 4 },
        { id: 5 },
        { id: 5 },
        { id: 5 },
        { id: 5 },
      ],
    };
  },
};
</script>
<style></style>
