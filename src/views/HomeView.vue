<template>
  <div class="home">
    <p>
      • Vos créations avec à chaque fois une image et un titre. Une modal s'ouvrira avec plus<br/>
      de photos et détails au clic. La disposition est libre.<br/>
      • Un formulaire de contact (nom/prénom, objet et message) qui s'envoie à l'adresse email définie en variable d'environnement.
    </p>
    <h2>Joseph LEVEQUE</h2>
    <p>Je me présente, ....................................</p>
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
        <button id="button" type="submit">Envoyer le message</button>
      </form>
  </div>
  
</template>

<script>

export default {
  name: 'HomeView',
  components: { }
}
</script>

<style lang="scss">

.home {
  background-color: rgba(0, 0, 0, 0.836);
  padding: 3em 6em 1em 6em;
}

#form {
  background-color: rgba(0, 0, 0, 0.836);
  padding: 1em 6em 3em 6em;
}

form {
  width: 400px;
  padding: 1em;
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
  /* Taille et alignement uniformes */
  display: inline-block;
  width: 90px;
  text-align: center;
}

input, textarea {
  font: 1em sans-serif;
  width: 300px;
  box-sizing: border-box;
  border: 1px solid #999;
}

textarea {
  /* On aligne les textes sur plusieurs lignes avec leur
     libellé. */
  vertical-align: top;

  /* On fournit un peut d'espace pour saisir du texte. */
  height: 5em;

  /* On permet de redimensionner verticalement. */
  resize: vertical;
}

.button {
  /* On aligne les boutons avec les champs texte. */
  padding-left: 90px; /* La même taille que les libellés */
}

button {
  /* Une marge supplémentaire représentant approximativement
     le même espace qu'entre les libellés et les champs. */
  margin-left: 0.5em;
}

</style>