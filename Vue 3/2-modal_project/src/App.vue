<template>
  <h1>{{ title }}</h1>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up Now</a>
        <a href="#">More Info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </teleport>
  <teleport to=".modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign Up to the Newsletter</h1>
      <p>For Updates and Promo Codes</p>
    </Modal>
  </teleport>
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open Modal 2</button>
  <Log />
</template>

<script>
import Modal from "./components/Modal.vue";
import Log from "./components/Log.vue";

export default {
  name: "App",
  components: { Modal, Log },
  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app,
.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
input,
button {
  display: block;
  margin: 0 auto;
  margin-top: 6px;
}
</style>
