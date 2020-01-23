<template>
  <div id="app">
    <div id="nav">
      <div class="nav-bar">
        <img class="logo" src="./assets/Logo_v1.png" />
      </div>
      <div class="nav-items-container">
        <div class="nav-item">Jewelry</div>
        <div class="nav-item">Clothing</div>
        <div class="nav-item">Nutrition</div>
        <div class="nav-item">Example</div>
      </div>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
.nav-items-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  margin: auto;
  height: 30px;
  background-color: rgb(255, 153, 197);
}

.nav-item {
  margin: auto;
  color: white;
}

.nav-bar {
  display: grid;
  height: 60px;
  background-color: transparent;
  /* border-bottom: solid 3px #FFCAE1; */
  margin: auto;
  grid-template-columns: 255px 1fr;
  grid-template-rows: 60px 40px;
  z-index: 1;
}

.logo {
  width: 200px;
  margin: auto;
  /* filter: saturate(250%); */
}

@media only screen and (max-width: 900px) {
  .nav-bar {
    grid-template-columns: 1fr;
  }
}
</style>
