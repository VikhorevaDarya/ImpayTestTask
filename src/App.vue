<template>
  <button @click="onShow">Show modal</button>
  <ModalComponent ref="modal">
    "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
    quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
    consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
    cillum dolore eu fugiat nulla pariatur."
  </ModalComponent>
</template>

<script>
import { ref } from "vue";
import ModalComponent from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    ModalComponent,
  },
  data() {
    const modal = ref(null);
    const onShow = async () => {
      this.$refs.modal.show().then((action) => {
        console.log("resolve", action);
      });
    };

    return {
      onShow,
      modal,
    };
  },
  methods() {},
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
}
</style>
