<template>
  <div
    v-if="modal"
    @click="closeModalHere"
    class="w-[100%] left-[0%] fixed top-[0%] overflow-y-auto min-h-[100%] bg-gray-500/90 z-50"
  ></div>
  <div
    v-if="modal"
    class="w-[90%] left-[5%] rounded-md absolute top-[5%] min-h-[90%] overflow-y-auto bg-white z-50"
  >
    <div class="absolute right-4 top-4">
      <svg
        @click="closeModalHere"
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="currentColor"
        class="w-6 h-6"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M6 18 18 6M6 6l12 12"
        />
      </svg>
    </div>
    <slot />
  </div>
</template>

<script setup>
import { defineProps } from "vue";
const props = defineProps({
  modal: Boolean,
  closeModal: Function,
});

const closeModalHere = () => {
  props.closeModal(true);
};
</script>
