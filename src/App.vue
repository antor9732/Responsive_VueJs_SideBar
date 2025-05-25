<script setup>
import Sidebar from "./components/Sidebar.vue"
</script>

<template>
  <div class="app">
    <Sidebar />

    <router-view />
  </div>
</template>

<style lang="scss">
:root {
 --primary: #5e81f4;
 --dark: #1e1e1e;
 --light: #dddddd;
  --white: #ffffff;
  --black: #000000;
  --light-blue: #53a1da;
  --dark-blue: #1a73e8;
  --light-green: #a5d6a7;
  --dark-green: #388e3c;
  --light-red: #ff8a80;
  --dark-red: #d32f2f;
 --light-yellow: #fff9c4;
 --dark-yellow: #fbc02d;
 --grey: #e0e0e0;
 --dark-grey: #333333;
 --red: #e53935;
 --green: #00c853;
 --blue: #2196f3;
 --yellow: #ffca28;
 --sidebar-width: 300px;
}
* {
  margin : 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Fira sans", sans-serif;
}
body {
  background : var(--light);
  color: var(--dark);
}
button{
  cursor: pointer;
  appearance: none;
  border: none;
  outline: none;
  background: none;
}

.app {
  display: flex;

}
.app main {
    flex: 1 1 0;
    padding: 2rem;
    @media (max-width: 768px) {
      padding-left: 6rem;
    }
  }
</style>
