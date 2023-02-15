<template>
  <div id="app">
    <h1>Contacts</h1>
    
    <div id="nav">
    </div>
    <router-view/>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css?family=Open+Sans&display=swap");
 h1 {
    margin: 0;
    padding: 0;
    font-size: 2.5rem;
 }
html{
  background: linear-gradient(
    to right,
    #ffc080,
    #ff80c0
  );
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
   width: 500px;
  max-width: 100%;
  margin: 0 auto;

}

</style>
