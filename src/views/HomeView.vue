<template>
  <main>
  <div class="home">
    <div class="présentation">
      <p>
        • Vos créations avec à chaque fois une image et un titre. Une modal s'ouvrira avec plus<br/>
        de photos et détails au clic. La disposition est libre.<br/>
      </p>
      <h2 id="presentation">Présentation</h2>
      <h3>Joseph LEVEQUE</h3>
    <p>Je me présente, ....................................</p>
    </div>
    <div class="blockmodalcv">
      <h2 id="project">Mes projets</h2>
      <button class="modalcv" @click="openModal">
        <h2>Mon CV</h2>
        <div class="image-overlay">
          <img class="imagesitecv" src="../assets/Images/sitecv.png"  alt="Image site CV">
        </div>
      </button>
      <ModalCV ref="modal"/>
    </div>
  </div>
  <div id="form">
    <h2 id="contact">Contact</h2>
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
          <button class="buttonform" type="submit">Envoyer le message</button>
        </div>
      </form>
    </div>
    </main>
      <footer>
      <section id="socialLink">
        <!--Social links with link to account and actualisation date -->
        <a style="color: rgb(255, 255, 255);" href="https://github.com/Lordprotos"><img id="logoGithub" src="@/assets/Images/GitHub.png" alt="Logo GitHub" /><br />GitHub</a>
        <a style="color: rgb(255, 255, 255);" href="https://www.linkedin.com/in/joseph-leveque-10213329b/"><img id="logoLinkedin" src="@/assets/Images/Linkedin.png" alt="LogoLinkedin" /><br />Linkedin</a>
        <a style="color: rgb(255, 255, 255);" href="https://twitter.com/protos241"><img id="logoTwitter" src="@/assets/Images/Twitter.png" alt="Logo Twitter"><br>Twitter</a>
        <p id="time"><strong>Cette page à été actualisée le <time datetime="2024-02-26">26 février 2024</time></strong></p>
      </section>
    </footer>
  
  
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
  },
    scrollToSection(sectionId) {
      this.$emit('scroll-to-section', sectionId);
  },
};


</script>

<style lang="scss">

div .home {
  padding: 2em 2em 2em 2em;
}
div .blockmodalcv {
  padding: 1em;
}

div .présentation {
  padding-left: 1em;
}

h2 {
  text-decoration: underline;
  width: max-content;
  cursor: pointer;
}

.home h2:hover {
  color: rgb(66, 66, 233);
}

.home {
  background-color: rgba(0, 0, 0, 0.541);
  padding: 3em 6em 1em 6em;
  display: flex;
  flex-direction: column;
}

#form {
  background-color: rgba(0, 0, 0, 0.541);
  padding: 1em 4em 3em 6em;
}

form {
  width: 400px;
  padding: 2em 2em 2em 1em;
  margin-left: -3em;
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
  text-align: right;
  margin-right: 10px;
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

.buttonform:hover {
  background-color: black;
  color: white;
  border-color: white;
}

.modalcv {
  margin-left: 0;
  margin-top: 5px;
  padding: 2em;
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