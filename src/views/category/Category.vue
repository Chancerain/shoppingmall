<template>
  <div class="wrapper" ref="aaa">
    <ul class="content">
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
    </ul>
  </div>
</template>

<script>
import BScroll from "better-scroll";
import ScrollVue from "../../../../coderwhy-supermall-master/src/components/common/scroll/Scroll.vue";

export default {
  name: "Category",
  data() {
    return {
      scroll: null,
    };
  },
  created() {
    // this.scroll = new BScroll(".content", {});
  },
  mounted() {
    this.scroll = new BScroll(document.querySelector(".wrapper"), {});
  },
};
</script>

<style scoped>
.wrapper {
  height: 150px;
  background-color: red;
  overflow: hidden;
}
</style>