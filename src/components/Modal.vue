<template>
    <div class="backdrop">
        <div class="modal">
            <h1>Modal Title</h1>
            <p>Modal content</p>
        </div>
    </div>
</template>

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
</style>