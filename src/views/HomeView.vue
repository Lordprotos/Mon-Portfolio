<template lang="fr">
  <main>
  <div class="home">
    <!--block prentation-->
    <h2 id="presentation">Présentation</h2>
    <div class="présentation">
      <div class="blockpresentation">
        <h3>Joseph LEVEQUE</h3>
        <p class="textpresentation">Je me présente, je suis un jeune développeur web de 23 ans passioné de jeux videos, plein d'ambition
          et à la recherche de nouvelle connaisance.<br> Je suis motivié dans ce que j'entreprend et n'abandonne
          pas facilement, je ne suis de base pas tres sociable mais je fais en sorte que ca n'affecte pas mon travaille.<br> J'ai une attitude 
          differente lorsque que je suis concentrer sur mon travaille, je suis minutieux au possible et j'aime proposée et montré un résultat propre.
        </p>
      </div>
      <!--block language-->
      <div class="blocklangue">
        <h3>Langues parlées</h3>
          <ul>
            <li>Francais - Langue maternelle</li>
            <li>Anglais - Intermédiaire</li>
          </ul>
        <h3>Maitrise des languages</h3>
          <ul>
            <li>HTML 5 : Intermédiaire</li>
            <li>CSS 3 : Intermédiaire</li>
            <li>JavaScript : Débutant</li>
            <li>VueCLI : Débutant</li>
          </ul>
      </div>
      <!--block interet-->
      <div class="blockinteret">
          <h3>Centres d'interêts</h3>
          <ul>
            <li>Jeux videos</li>
            <li>Anime</li>
            <li>Manga</li>
            <li>Astronomie</li>
          </ul>
      </div>
    </div>
    <!--block modal-->
    <div class="blockmodalcv">
      <h2 id="project">Mes projets</h2>
      <button class="modalcv" @click="openModal">
        <h2>Mon CV</h2>
        <div class="image-overlay">
          <img class="imagesitecv" src="../assets/Images/sitecv.png"  alt="Image site CV">
        </div>
      </button>
      <ModalCV ref="modal"></ModalCV>
    </div>
  </div>
  <!--block form-->
  <div id="form">
    <h2 id="contact">Contact</h2>
      <form @submit.prevent="showAlert">
        <ul>
          <li>
            <label for="firstname">Nom : </label>
            <input type="text" id="firstname" name="user_firstname">
          </li>
          <li>
            <label for="lastname">Prénom : </label>
            <input type="text" id="lastname" name="user_lastname">
          </li>
          <li>
            <label for="email">Email : </label>
            <input type="email" id="user_email" name="user_email">
          </li>
          <li>
            <label for="">Laisser un message : </label>
            <textarea name="message" id="message" cols="30" rows="10"></textarea>
          </li>
        </ul>
        <div class="button-container">
          <button class="buttonform" type="submit">Envoyer le message</button>
        </div>
      </form>
    </div>
    </main>
    <!--footer-->
      <footer>
      <section id="socialLink">
        <!--Social links with link to account and last update-->
        <a style="color: rgb(255, 255, 255);" href="https://github.com/Lordprotos"><img id="logoGithub" src="@/assets/Images/GitHub.png" alt="Logo GitHub" /><br />GitHub</a>
        <a style="color: rgb(255, 255, 255);" href="https://www.linkedin.com/in/joseph-leveque-10213329b/"><img id="logoLinkedin" src="@/assets/Images/Linkedin.png" alt="LogoLinkedin" /><br />Linkedin</a>
        <a style="color: rgb(255, 255, 255);" href="https://twitter.com/protos241"><img id="logoTwitter" src="@/assets/Images/Twitter.png" alt="Logo Twitter"><br>Twitter</a>
      </section>
      <p id="time"><strong>Cette page à été actualisée le <time datetime="2024-03-06">6 mars 2024</time></strong></p>
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
},
scrollToSection(sectionId) {
this.$emit('scroll-to-section', sectionId);
},
showAlert() {
console.log('La méthode showAlert est appelée !');
const firstName = document.getElementById('firstname').value;
const lastName = document.getElementById('lastname').value;
const email = document.getElementById('user_email').value;
const message = document.getElementById('message').value;

console.log('Nom :', firstName);
console.log('Prénom :', lastName);
console.log('Email :', email);
console.log('Message :', message);

console.log('Affichage de l\'alerte !');
alert('Le mail a été envoyé !');
}
}
};
</script>

<style lang="scss">

/*style page home --------------------*/

.home {
  background-color: rgba(0, 0, 0, 0.541);
  padding: 3em 6em 1em 6em;
  display: flex;
  flex-direction: column;
}

div .présentation {
  padding-left: 1em;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.présentation div {
  width: 25vw;
  text-align: center;
}

/*style h2 --------------------*/

h2 {
  padding: 0 0 0 20px;
  text-decoration: underline;
  width: max-content;
}

/*style form --------------------*/

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

/*style modal --------------------*/

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
  max-width: max-content;
  max-height: max-content;
}

div .blockmodalcv {
  padding: 1em;
}

.blockmodalcv h2 {
  color: white;
}

.modalcv:hover {
  box-shadow: 5px 5px 3px rgb(84, 196, 90);
}

.imagesitecv {
  width: 200px;
  height: 200px;
  margin: 0;
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 2px solid white;
  border-radius: 30px;
}

/*style footer --------------------*/

footer {
  margin: 3em;
}

#socialLink {
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin-left: 30px;
    gap: 20px;
}

#socialLink a:hover {
  color: blue !important;
  text-shadow: 13px 13px rgb(84, 196, 90);
}

#time {
  display: flex;
  flex-direction: row-reverse;
}

</style>