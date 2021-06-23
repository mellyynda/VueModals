<template>
<h1>{{ title }}</h1>
<teleport to=".modals" v-if="showModal">
  <Modal theme="sale" @close="toggleModal" >
    <template v-slot:links>
      <a href="">sign up now</a>
      <a href="">more info</a>
    </template>
    <h1>Ninja Giveaway!</h1>
    <p>Grab your ninja swag for half price</p>
  </Modal>
</teleport>
<teleport to=".modals" v-if="showModalTwo">
  <Modal theme="dark" @close="toggleModalTwo" >
    <template v-slot:links>
      <a href="">Buy now</a>
    </template>
    <h1>New things to buy</h1>
    <p>Get some new stuff every day and throw the old ones to the trash. Keep wasting and you shall be king of wasteland!</p>
  </Modal>
</teleport>
<p>welcome</p>
<button @click="toggleModal">open modal </button>
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio placeat officiis quia, alias ad, libero inventore vero magni nobis impedit tempora explicabo error voluptate quisquam laboriosam asperiores, repellendus ut. Doloremque.</p>
<button @click="toggleModalTwo">see the new stuff</button>
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
      showModal: false,
      showModalTwo: false
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
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    }
  }
}
</script>

<style>
#app, .modals {
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
