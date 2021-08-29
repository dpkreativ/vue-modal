<template>
  <div
    id="modal-backdrop"
    class="fixed inset-0 bg-opacity-20 bg-purple-800 flex justify-center items-center"
  >
    <div
      id="modal"
      class="bg-purple-50 rounded-3xl overflow-x-auto flex flex-col justify-between w-2/5 h-3/5"
    >
      <!-- Modal Header -->
      <header
        id="modal-header"
        class="p-4 flex justify-between items-center border-b-2 border-white text-purple-900"
      >
        <slot name="header">Dummy header</slot>
        <button
          type="button"
          class="w-7 p-2 bg-gray-300 rounded-full"
          @click="close"
        >
          <img src="../assets/letter-x.svg" alt="close button" />
        </button>
      </header>

      <!-- Modal Body -->
      <section id="modal-body" class="px-4 py-6">
        <slot name="body"></slot>
      </section>

      <!-- Modal Footer -->
      <footer id="modal-footer" class="px-4 py-6 border-t-2 border-white">
        <slot name="footer"></slot>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  methods: {
    close() {
      this.$emit("close");
    },
  },
};
</script>

<style></style>
