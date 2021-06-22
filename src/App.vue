<template>
<h1>{{ title }}</h1>
<input type="text" ref="name">
<button @click="handleClick">click me</button>
<div v-if="showModal">
  <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
</div>
  <p>welcome</p>
<button @click="toggleModal">open modal </button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: "My First Vue App :)",
      header: "Sign-up for the giveaway!",
      text: "Grab your new sthg for half price now.",
      showModal: false
    }
  },
  methods: {
    handleClick() {
      // console.log(this.$refs.name.value);
      // this.$refs.name.classList.toggle('active');
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display:inline-block;
  padding-bottom: 10px;
}
.active{
  background:honeydew;
  color:indianred;
}
</style>
