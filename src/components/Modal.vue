<template>
  <ModalDialog
    @cancel="onAction"
    @submit="onAction"
    v-if="isShow"
  >
    <slot />
  </ModalDialog>
</template>

<script>
import { ref } from "vue";
import ModalDialog from "@/components/ModalDialog";

export default {
  name: "ModalComponent",
  components: {
    ModalDialog,
  },
  data() {
    const isShow = ref(false);
    const actionElement = ref(false);
    const promise = ref(null);

    const onAction = (event) => {
      actionElement.value = event.target;
      isShow.value = false;

      promise.value(event.target.getAttribute("type"));
    };

    const show = async () => {
      isShow.value = true;

      return new Promise((resolve) => {
        promise.value = resolve;
      });
    };

    return {
      isShow,
      show,
      onAction,
    };
  },
};
</script>

<style lang="less" scoped></style>
