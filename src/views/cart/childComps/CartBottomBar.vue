<template>
  <div class="bottom-bar">
    <div class="check-content">
      <check-button
        :is-checked="isSelectAll"
        class="check-button"
        @click.native="checkClick"
      />
      <span>全选</span>
    </div>

    <div class="price">合计：{{ totalPrice }}</div>

    <div class="calculate">去计算({{ checkLength }})</div>
  </div>
</template>

<script>
import CheckButton from "components/content/checkButton/CheckButton";
import { mapGetters } from "vuex";

export default {
  name: "CartBottomBar",
  components: {
    CheckButton,
  },
  computed: {
    ...mapGetters(["cartList"]),
    totalPrice() {
      return (
        "¥" +
        this.cartList
          .filter((item) => {
            return item.checked;
          })
          .reduce((preValue, item) => {
            return preValue + item.newPrice * item.count;
          }, 0)
          .toFixed(2)
      );
    },
    checkLength() {
      return this.cartList.filter((item) => item.checked).length;
    },
    isSelectAll() {
      if (this.cartList.length === 0) return false;
      return this.cartList.every((item) => item.checked);
    },
  },
  methods: {
    checkClick() {
      // if (this.isSelectAll) {
      //   this.cartList.forEach(item => item.checked = false)
      // } else {
      //   this.cartList.forEach(item => item.checked = true)
      // }
      this.cartList.forEach((item) => (item.checked = !this.isSelectAll));
    },
  },
};
</script>

<style scoped>
.bottom-bar {
  height: 40px;
  background-color: #eee;
  position: relative;
  bottom: 137px;
  display: flex;
}
.check-content {
  display: flex;
  align-items: center;
  margin-left: 10px;
  width: 80px;
}
.check-button {
  width: 20px;
  height: 20px;
  line-height: 20px;
  margin-right: 5px;
  margin-top: 4px;
}
.check-content span {
  margin-top: 4px;
  margin-right: 10px;
}
.price {
  margin-top: 12px;
  flex: 1;
}

.calculate {
  padding-top: 12px;
  width: 100px;
  background-color: red;
  text-align: center;
}
</style>