<template>
  <div class="modal" v-if="isVisible" @click.self="closeModal">
    <div class="modal-content" @click.stop>
      <span class="close" @click="close">&#10005;</span>
        <ul>
          <h1>Mon CV</h1>
          <p>Crée le 10/11/2023</p>
          <p>HTML5 / CSS </p>
          <p>lien pdf du site</p>
          <p>le repository GitHub</p>
          <a href="../assets/Images/sitecv.png"><img class="sitecv" src="../assets/Images/sitecv.png" alt="sitecv"></a>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
    name: 'ModalCV',
    data() {
      return{
        isVisible: false
      };
    },
    methods: {
      open() {
        this.isVisible= true;
      },
      close() {
        this.isVisible= false;
      },
      closeModal() {
      this.close();
    }
    }
};
</script>

<style>

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
  width: 60vmin; 
  height: 40vmin; 
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

.sitecv {
  width: 5em;
  height: 5em;
  display: inline-flex;
}

</style>

