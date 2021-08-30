<template>
  <button
    class="bg-white py-4 px-12 rounded-xl shadow-md"
    type="button"
    @click="showModal"
  >
    Open Modal
  </button>
  <Modal v-show="isModalVisible" @close="closeModal">
    <!-- header -->
    <template v-slot:header>
      <h1 class="font-bold text-xl">Log in</h1>
    </template>

    <!-- body -->
    <template v-slot:body>
      <input
        type="email"
        name="email"
        id="email"
        placeholder="E-mail"
        class="rounded-2xl w-full p-3 my-1 shadow-md outline-none"
      />
      <input
        type="password"
        name="password"
        id="password"
        placeholder="Password"
        class="rounded-2xl w-full p-3 my-1 shadow-md outline-none"
      />
      <p class="py-3 text-xs font-bold text-purple-900">
        Forgot your password?
      </p>

      <button
        type="button"
        class="rounded-2xl bg-purple-800 shadow-md p-3 my-1 w-full text-white"
      >
        Login
      </button>
    </template>

    <!-- footer -->
    <template v-slot:footer>
      <p class="text-purple-900 text-xs font-bold">
        Already have an account? <a href="#">Sign up</a>
      </p>
    </template>
  </Modal>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      isModalVisible: false,
    };
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
  },
};
</script>

<style>
body {
  background-color: #f0f0f0;
}
#app {
  font-family: "Nunito", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
