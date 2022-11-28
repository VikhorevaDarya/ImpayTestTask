<template>
  <div class="modal__overlay">
    <div class="modal">
      <h2 class="modal__header">Modal Dialog</h2>
      <slot class="modal__content" />
      <div class="modal__footer">
        <button
          type="submit"
          class="modal__button modal__button_submit"
          @click="onSubmit"
        >
          Submit
        </button>
        <button
          type="button"
          class="modal__button modal__button_cancel"
          @click="onCancel"
        >
          Cancel
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalDialog",
  props: {
    content: { type: String, default: "" },
  },
  emits: ["submit", "cancel"],
  data() {
    return {
      onSubmit: (event) => {
        this.$emit('submit', event)
      },
      onCancel: (event) => {
        this.$emit('submit', event)
      },
    };
  },
};
</script>

<style lang="less" scoped>
.modal {
  background-color: white;
  padding: 20px;
  width: 480px;
  border-radius: 15px;

  &__overlay {
    position: fixed;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    width: 100vw;
    top: 0;
    left: 0;
    z-index: 1;
    background-color: rgba(0, 0, 0, 0.6);
  }

  &__header {
    color: black;
  }

  &__footer {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
    width: 100%;
  }

  &__button {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 15px;
    font-size: 14px;
    background-color: blue;
    color: white;
    border: none;
    border-radius: 15px;
    cursor: pointer;

    &_sumbit {
    }

    &_cancel {
    }
  }
}
</style>
