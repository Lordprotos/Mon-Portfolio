<template>
  <div class="home">
    <p>
      • Vos créations avec à chaque fois une image et un titre. Une modal s'ouvrira avec plus<br/>
      de photos et détails au clic. La disposition est libre.<br/>
    </p>
    <h2>Joseph LEVEQUE</h2>
    <p>Je me présente, ....................................</p>
    <div class="blockmodalcv">
      <button class="modalcv" @click="openModal">
        <h2>Mon CV</h2>
        <div class="image-overlay">
          <img class="imagesitecv" src="../assets/Images/sitecv.png"  alt="Image site CV">
        </div>
      </button>
      <ModalCV ref="modal" />
    </div>
  </div>
  <div id="form">
      <form action="/send-email" method="post">
        <ul>
          <li>
            <label for="firstname">Nom : </label>
            <input type="text" id="email" name="user_name">
          </li>
          <li>
            <label for="lastname">Prénom : </label>
            <input type="text" id="email" name="user_name">
          </li>
          <li>
            <label for="email">Email : </label>
            <input type="email" id="email" name="user_email">
          </li>
          <li>
            <label for="">Laisser un message : </label>
            <textarea name="message" id="msg" cols="30" rows="10"></textarea>
          </li>
        </ul>
        <div class="button-container">
          <button type="submit">Envoyer le message</button>
        </div>
        
      </form>
  </div>
  
</template>

<script>

import ModalCV from './ModalCV.vue'

export default {
  name: 'HomeView',
  components: {
    ModalCV 
},
methods: {
    openModal() {
      this.$refs.modal.open();
    }
}
};


</script>

<style lang="scss">

.home {
  background-color: rgba(0, 0, 0, 0.541);
  padding: 3em 6em 1em 6em;
  display: flex;
  flex-direction: column;
  
}

#form {
  background-color: rgba(0, 0, 0, 0.541);
  padding: 1em 6em 3em 6em;
}

form {
  width: 400px;
  padding: 50px;
  border: 1px solid #ccc;
  border-radius: 1em;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

form li + li {
  margin-top: 1em;
}

label {
  display: inline-block;
  width: 90px;
  text-align: center;
}

input {
  caret-color: red;
}

input, textarea {
  font: 1em sans-serif;
  width: 300px;
  box-sizing: border-box;
  border: 1px solid #999;
}

textarea {
  vertical-align: top;
  height: 5em;
  resize: vertical;
}

.button-container {
  text-align: right;
  padding: 10px;
}

.modalcv {
  margin-left: 0;
  margin-top: 5px;
  padding: 3px;
  background: rgba(0, 0, 0, 0.5);
  border: 5px solid white;
  border-radius: 15%;
}

.blockmodalcv {
  text-align: left;
}

.blockmodalcv h2 {
  color: white;
}

.imagesitecv {
  width: 200px;
  height: 200px;
  margin: 0;
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 2px solid white;
}

</style>