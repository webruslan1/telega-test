<template>
  <div id="app">
    <Menu />
    <Header title="heading" />
    <Increase title="test title" />
    <Sorting title="sorting" />
  </div>
</template>

<script>
import Menu from "./components/Menu";
import Header from "./components/Header";
import Increase from "./components/Increase";
import Sorting from "./components/Sorting";
export default {
  name: "App",
  components: {
    Menu,
    Header,
    Increase,
    Sorting,
  },
};
</script>

<style>
html,
body {
  padding: 0;
  margin: 0;
}
#app {
  font-family: Roboto, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #f4f4f4;
  font-size: 62%;
  line-height: 12px;
  color: #000000;
  box-sizing: border-box;
  overflow: hidden;
}

h2 {
  text-transform: uppercase;
  margin: 0;
  font-family: Roboto, sans-serif;
  font-weight: bold;
  font-size: 14px;
  line-height: 16px;
  color: #000000;
}

section {
  margin: 0 auto;
  margin: 20px auto;
  padding: 20px;
  box-sizing: border-box;
}

section:nth-child(even) {
  width: 90%;
  background: #ffffff;
  border-radius: 15px;
}

section:nth-child(odd) {
  width: 100%;
  background: #c4c4c4;
}
button {
  display: inline;
  text-transform: uppercase;
  width: 50%;
  height: 45px;
  background: #fff;
  border: 2px solid #f4f4f4;
  box-sizing: border-box;
  border-radius: 15px;
  cursor: pointer;
  text-align: center;
}
.tac {
  text-align: center;
}
.mb-10 {
  margin-bottom: 10px;
}
.mb-15 {
  margin-bottom: 15px;
}
.mb-20 {
  margin-bottom: 20px;
}
</style>
