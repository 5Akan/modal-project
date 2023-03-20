<template>
    <div class="backdrop" @click.self  ="closeModal">
        <div class="modal" :class = "{sale:theme === 'sale'}">
            <h1>{{header}}</h1>
            <p>{{text}}</p>
        </div>
    </div>
</template>

<script>
export default {
        props:['header','text','theme'],
        methods:{
            closeModal(){
                //Custom Events ($emit) can be fired from the modal and listened too from the parent(App.vue)
                this.$emit('close');
            }
        }
    }
</script>
    
<style scoped>
    .modal{
        width:400;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }
    h1{
        color: #03cfb4;
        border: none;
        padding: 0;
    }
    .modal.sale{
        background: crimson;
        color: white;
    }
    .modal.sale h1{
        color: white;
    }
</style>