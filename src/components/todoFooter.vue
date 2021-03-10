<template>
  <div class="footer">
    <footer-stadistics />
    <span class="footerText"
      >To do List App <br />
      with Vue <br />Developed by Jonás</span
    >
  </div>
</template>
<script>
import footerStadistics from "./footerStadistics.vue";
export default {
  components: { footerStadistics },
};
</script>
<style lang="scss" scoped>
.footer {
  display: grid;
  grid-template-columns: 50% 50%;
  padding-top: 1vw;
  padding-bottom: 1vw;
  background-color: #dad1f5;
  font-size: 1vw;
}
.footerText {
  padding-top: 1vw;
}
</style>