<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
.user-item{
  background-color: #eee;
  margin:10px;
  padding-top: 10px;
}
.user-item img{
  width: 50px;
  height: auto;
  background: #a0a261;
}
.user-item .immg{
  float: left;
  margin-right: 10px;
}
.prof{
  float: left;
}
.user-item span{
  font-weight: bold;
}
.user-item a{
  margin:0;
  clear: both;
  float: left;
}
.listaDetalles{
  background: #ffffff;
  width: 100%;
}

</style>
