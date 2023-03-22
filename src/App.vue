<template>
  <h1>{{title}}</h1>
  <!-- <input type="text" ref="name">
  <button @click ="handleClick">Click Me</button>-->
  <teleport to =".modals" v-if="showModal"> 
    <Modal  theme ="sale" @close="toggleModal"><!--Prop is the string assigned to the name header-->
    <!-- @close is the custom event listened to from the modal.vue -->
    <!-- SLOT -->
    <!-- Below show up in slot tag of Modal by default -->
    <h1>Bring It</h1>
    <p>Trying Something New</p>
    <!-- Below are inside a temp and wont show in Slot tag by default -->
    <template v-slot:links>
      <a href="a">sign up now</a>
      <a href="a">more info</a>
    </template>
    </Modal>
  </teleport>
  <teleport to = ".modals" v-if="showModalTwo">
    <Modal @close = "toggleModalTwo">
      <template v-slot:linkstwo>
      <p>The Challenge</p>
    </template>
    </Modal>
  </teleport>
  <button @click.alt ="toggleModal">Open Modal (alt)</button>
  <button @click="toggleModalTwo">Challenge</button>
  <!-- Click Event Modifiers eg @click.alt -->

</template>

<script>
import Modal from './components/Modal.vue';
export default {
  name: 'App',
  components:{ Modal },
  data(){
    return{
      title:'My First Vue App ♫',
      header:"Sign up for the Giveaway!",
      text:"It was made by me",
      showModal:false,
      showModalTwo:false
    }
  },
  methods:{
    //  handleClick(){
    //     console.log(this.$refs.name);
    //     this.$refs.name.classList.add('active');
    //  },
     toggleModal(){
       this.showModal=!this.showModal;
     },
     toggleModalTwo(){
       this.showModalTwo=!this.showModalTwo;
     }

  }
}
</script>

<style>
#app , .modals{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

 h1{
    border-bottom: 1px solid #ddd;
    padding-bottom: 10px;
  }
button{
  color: #2c3e50;
}

</style>
