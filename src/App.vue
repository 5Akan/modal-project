<template>
  <h1>{{title}}</h1>
  <!-- <input type="text" ref="name">
  <button @click ="handleClick">Click Me</button>-->
  <div v-if="showModal"> 
    <Modal :header="header" :text = "text" theme ="sale"/><!--Prop is the string assigned to the name header-->
  </div>
  <button @click="toggleModal">
      <span v-if="showModal">Hide</span>
      <span v-else>Show</span>
    </button>
  

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
      showModal:false
    }
  },
  methods:{
    //  handleClick(){
    //     console.log(this.$refs.name);
    //     this.$refs.name.classList.add('active');
    //  },
     toggleModal(){
       this.showModal=!this.showModal;
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
    padding-bottom: 10px;
  }
button{
  color: #2c3e50;
}
</style>
