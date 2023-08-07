<template>
    <div class="modal-bg" @click.self="closeModal">
      <div class="modal"> 
        Modal
        <button @click="closeModal">Close modal</button>
      </div>
    </div>
  </template>
  
  <script>
    export default {
      props: [],
      methods: {
        closeModal() {
          this.$emit('onClose');
        }
      }
    }
  </script>
  
  <style>
    .modal-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100vh;
      background-color: rgba(0,0,0,.5);
      display: flex;
      justify-content: center;
      align-items: center;
    }
  
    .modal {
      width: 300px;
      background-color: #fff;
      border-radius: 10px;
      padding: 20px;
    }
  </style>