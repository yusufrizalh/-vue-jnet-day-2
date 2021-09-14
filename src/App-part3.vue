<template>
  <h1>{{ title }}</h1>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
        <h1>Coupon Giveaway!</h1>
        <p>Grab your coupon for half price!</p>
        <template v-slot:links>
            <a href="#">Signup now</a>
            <a href="#">More info</a>
        </template>
    </Modal>
  </teleport> <br>
  <button @click="toggleModal">open modal</button> <br> <br>
  <button @click.alt="toggleModal">open modal (alt)</button>
</template>

<script>
// import components
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  data() {
    return {
      title: "My First Vue App :)",
      header: "Signup for Giveaway!",
      text: "Grab your coupon for half price!",
      showModal: false,
    };
  },
  components: { Modal },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #e9e9e9;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
