<template>
<div id="app">
  <header>
    <img src="../src/assets/Images/House.svg" alt="House">
    <nav>
        <router-link to="/">Home</router-link> |
        <router-link to="/MyPage">My Page</router-link> |
        <router-link to="/ErrorPage">Erreur 404</router-link>
      </nav>
  </header>
  <main>
    <router-view/>
  </main>
  <footer>
      <section id="socialLink">
        <!--Social links with link to account and acutalisation date -->
        <a href="https://github.com/Lordprotos"><img id="logoGithub" src="../src/assets/Images/GitHub.png" alt="Logo GitHub" /><br />GitHub</a>
        <a href="https://www.linkedin.com/in/joseph-leveque-10213329b/"><img id="logoLinkedin" src="../src/assets/Images/Linkedin.png" alt="LogoLinkedin" /><br />Linkedin</a>
        <a href="https://twitter.com/protos241"><img id="logoTwitter" src="../src/assets/Images/Twitter.png" alt="Logo Twitter"><br>Twitter</a>
        <p id="time"><strong>Cette page à été actualisée le <time datetime="2024-02-12">12 février 2024</time></strong></p>
      </section>
    </footer>
</div>
</template>

<style lang="scss">
#app {
  background: linear-gradient(to left, rgb(0, 25, 248), rgb(126, 24, 129), rgb(116, 116, 56), rgb(167, 58, 58), rgb(116, 116, 56), rgb(126, 24, 129), rgb(0, 25, 248));
  animation: gradientAnimation 10s infinite alternate; 
  background-size: 600% 600%;
  font-size: medium;
  text-align: center;
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
  background: none;
}

nav {
  a {
    font-weight: bold;
    color: #ce66dbaf;

    &.router-link-exact-active {
      color: #7de2b4;
    }
  }
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
    height: 100px 
}
</style>
