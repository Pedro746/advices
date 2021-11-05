<template>
  <div id="nav">
    <router-link to="/">Conselhos</router-link> |
    <router-link to="/about">Info</router-link>
  </div>
  <router-view/>
</template>

<style>

@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@200;300;400;600;700;800&display=swap");
* {
  font-family: "Nunito", sans-serif;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: #7159C1;
  text-decoration: none;
}
</style>
