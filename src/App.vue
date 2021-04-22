<template>
  <div id="app">
    <div id="nav">
      <div class="nav_sx">
        <h1>BEERS</h1>
      </div>
      <div class="nav_dx">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<style>

@import url('https://fonts.googleapis.com/css2?family=Khula&display=swap');

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;

}

#app {
  font-family:  'Khula', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;


  min-height: 100vh;

  background-image: url("assets/beer_background.jpg");
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

#nav {
  padding: 30px;
  height: 40px;
  background-color: rgb(0, 0, 0);
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid grey;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  padding-top: 2px;
  padding-bottom: 1px;
  padding-left: 1px;
  padding-right: 1px;
  border-radius: 5px;
  color: rgb(196, 139, 74);
  border: 1px solid white;
}

</style>
