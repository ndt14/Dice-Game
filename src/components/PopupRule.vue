<template>
  <div class="popup" :class="getClassPopup">
    <div class="rule">
      <h1>Luật chơi</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil provident in deleniti sed mollitia beatae ipsam
        numquam, excepturi repudiandae neque fuga, fugiat, ducimus voluptatem nesciunt nulla? Deserunt consectetur
        quibusdam nihil?
      </p>
      <button v-on:click="confirm" class="confirm">Đã Hiểu</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'popup-rule',
  props: {
    isOpenPopup: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    confirm() {
      this.$emit('handleConfirm');
    },
  },
  computed: {
    getClassPopup() {
      return {
        'open-popup': this.isOpenPopup,
      };
    },
  },
};
</script>

<style>
.popup {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0);
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
}
.open-popup {
  opacity: 1;
  visibility: visible;
}
.rule {
  width: 350px;
  height: 200px;
  background-color: #fff;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) scale(1.2);
  position: absolute;
  transition: all 0.3s ease;
}
.open-popup .rule {
  transform: translate(-50%, -50%) scale(1);
}
.rule h1 {
  text-align: center;
  margin-top: 10px;
}
.rule .confirm {
  cursor: pointer;
  background-color: white;
  margin: 10px;
  transition: all 0.3s ease;
  padding: 10px;
  border: 1px solid black;
}
.rule .confirm:hover {
  color: white;
  background-color: black;
}
/* kết hợp css3 */
</style>