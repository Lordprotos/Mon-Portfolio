<template>
<div id="app">
  <header id="header">
    <nav id="nav">
        <router-link to="/" @click="scrollToTop"><img id="house" src="../src/assets/Images/House.svg" alt="House"><span>Home</span></router-link>
    </nav>
    <div class="title_nav">
      <h1 class="titre1">Mon Portfolio</h1>
      <nav class="nav2">
        <p @click="scrollToSection('presentation')">Présentation</p>
        <p @click="scrollToSection('project')">Mes projets </p>
        <p @click="scrollToSection('contact')">Contact</p>
      </nav>
    </div>
  </header>
  <main>
    <router-view/>
  </main>
</div>
</template>

<script>

export default {

  methods: {
    scrollToTop() {
      window.scrollTo({top:0, behavior: 'smooth' });
    },
    scrollToSection(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
}
</script>

<style lang="scss">

#app {
  background: linear-gradient(to left, rgb(54, 64, 153), rgb(46, 100, 172), rgb(167, 58, 58),  rgb(46, 100, 172), rgb(54, 64, 153));
  animation: gradientAnimation 30s infinite alternate; 
  background-size: 600% 600%;
  color: white;
}

div #app{
  padding: 2em;
}

footer {
  margin: 3em;

}

#header {
  padding: 10px 7% 3% 7%;
  margin: 10px;
}

@keyframes gradientAnimation {
  0% {
    background-position: 0% 50%; 
  }
  100% {
    background-position: 100% 50%; 
  }
}

#app main {
  font-size: 110%;
}

.title_nav {
  display: flex;
  flex-direction: column;
  justify-content: center; 
  align-items: center; 
  height: 9em;
}

.title_nav p {
  padding: 5px;
  text-decoration: underline;
}

.nav2 {
  display: flex;
  justify-items: flex-start;
  border: 3px solid rgb(255, 255, 255);
  border-radius: 20px;
  padding: 1em;
}

.nav2 p {
  text-decoration: underline;
  max-height: max-content;
  max-width: max-content;
  cursor: pointer;
}

.nav2 p:hover {
  color: rgb(61, 219, 69);
}


#nav {
  position: fixed;
  display: flex;
  align-items: center;
  font-size: 180%;
  border: 3px solid black;
  border-radius: 15px;
  padding: 5px;
  top: 50px;
  right: 50px;
  
}


#nav a {
  font-weight: bold;
  color: #1aace6af;
}

#nav a.router-link-exact-active {
  color: #111111;
  text-decoration: none;
}

#nav router-link {
  display: flex;
  align-items: center;
  text-decoration: none;
}

#nav span {
  margin-left: 13px;
}

.titre1 {
  border: 3px solid rgb(255, 255, 255);
  border-radius: 15px;
  padding: 5px;
  width: 193px;
}

#logoGithub {
    width: 50px;
    height: 50px;
}

#logoLinkedin {
    width: 57px;
    height: 50px;
}

#logoTwitter {
    width: 47px;
    height: 50px;
}

#time {
    display: flex;
    align-self: flex-end;
}

#logoPortfolio {
    width: 100px;
    height: 100px; 
}

#house {
  display: flex;
  width: 100px;
  height: 100px;
}

</style>
