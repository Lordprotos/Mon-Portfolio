<template>
<div id="app">
  <header id="header">
    <nav id="nav">
        <router-link to="/" @click="scrollToTop"><img id="house" src="../src/assets/Images/House.svg" alt="House"><span>Home</span></router-link>
    </nav>
    <h1 class="titre1">Mon Portfolio</h1>
  </header>
  <main>
    <router-view/>
  </main>
  <footer>
      <section id="socialLink">
        <!--Social links with link to account and actualisation date -->
        <a style="color: rgb(255, 255, 255);" href="https://github.com/Lordprotos"><img id="logoGithub" src="../src/assets/Images/GitHub.png" alt="Logo GitHub" /><br />GitHub</a>
        <a style="color: rgb(255, 255, 255);" href="https://www.linkedin.com/in/joseph-leveque-10213329b/"><img id="logoLinkedin" src="../src/assets/Images/Linkedin.png" alt="LogoLinkedin" /><br />Linkedin</a>
        <a style="color: rgb(255, 255, 255);" href="https://twitter.com/protos241"><img id="logoTwitter" src="../src/assets/Images/Twitter.png" alt="Logo Twitter"><br>Twitter</a>
        <p id="time"><strong>Cette page à été actualisée le <time datetime="2024-02-26">26 février 2024</time></strong></p>
      </section>
    </footer>
</div>
</template>

<script>

export default {
  methods: {
    scrollToTop() {
      window.scrollto({top:0, behavior: 'smooth' });
    }
  }
}
</script>

<style lang="scss">

#app {
  background: linear-gradient(to left, rgb(0, 25, 248), rgb(126, 24, 129), rgb(116, 116, 56), rgb(167, 58, 58), rgb(116, 116, 56), rgb(126, 24, 129), rgb(0, 25, 248));
  animation: gradientAnimation 10s infinite alternate; 
  background-size: 600% 600%;
  color: white;
}

div {
  padding: 2em;
}

footer {
  margin: 3em;
  
}

#header {
  display: flex;
  justify-content: space-between;
  align-items: center;
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
  font-size: 120%;
}



nav {
  position: fixed;
  display: flex;
  align-items: center;
  font-size: 180%;
  border: 3px solid black;
  border-radius: 15px;
  padding: 5px;
  
}

nav a {
  font-weight: bold;
  color: #1aace6af;
}

nav a.router-link-exact-active {
  color: #111111;
  text-decoration: none;
}

nav router-link {
  display: flex;
  align-items: center;
  text-decoration: none;
}

nav span {
  margin-left: 13px;
}

.titre1 {
  border: 3px solid rgb(255, 255, 255);
  border-radius: 15px;
  padding: 5px;
  margin-left: 40%;
}


#socialLink {
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin-left: 30px;
    gap: 20px;
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
