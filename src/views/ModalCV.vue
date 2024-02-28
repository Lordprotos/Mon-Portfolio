<template>
  <div class="modal" v-if="isVisible" @click.self="closeModal">
    <div class="modal-content" @click.stop>
      <span class="close" @click="close">&#10005;</span>
        <ul>
          <h1>Mon CV</h1>
          <p>Crée le 10/11/2023</p>
          <p>HTML5 / CSS </p>
          <p>le repository GitHub</p>
        </ul>
        <div class="sitecv-link">
          <a :href="imageURL" target="_blank"><img class="imagesite" :src="sitecvImage" alt="sitecv"></a>
        </div>
    </div>
  </div>
</template>

<script>
import sitecvImage from "@/assets/Images/sitecv.png";

import sitecvLargeImage from "@/assets/Images/sitecv_large.png";

export default {
  name: 'ModalCV',

data() {

  return {

    isVisible: false,

    sitecvImage: sitecvImage,

    imageURL: sitecvLargeImage 

  };

},
  methods: {
    open() {
      this.isVisible = true;
    },
    close() {
      this.isVisible = false;
    },
    closeModal() {
      this.close();
    }
  }
};
</script>

<style>

div .modal {
  padding: 2em;
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  display: flex;
  justify-content: space-around;
  width: 60vw; 
  height: auto; 
  background-color: rgba(0, 0, 0, 0.603);
  padding: 20px;
  border-radius: 10px;
  border: 2px solid #ccc; 
}

.close {
  position: absolute;
  top: 10px;
  right: 10px;
  cursor: pointer;
  font-size: 24px;
  color: black;
}

.imagesite {
  width: 300px;
  height: 300px;
}

</style>

