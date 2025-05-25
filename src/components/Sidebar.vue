<script setup>
import { ref } from "vue";

const is_expanded = ref(false);

const ToggleMenu = () => {
  is_expanded.value = !is_expanded.value;
};
</script>
<template>
  <aside :class="`${is_expanded && 'is_expanded'}`">
    <div class="logo">
      <img src="../assets/logo.svg" alt="vue" />
    </div>

    <div class="menu-toggle-wrap">
      <button class="menu-toggle" @click="ToggleMenu">
        <span class="material-icons">keyboard_double_arrow_right</span>
      </button>
    </div>
    <h1>Menu</h1>
    <div class="menu">
       <router-link class="button" to="/">
        <span class="material-icons">home</span>
        <span class="text">Home</span>
       </router-link>
       <router-link class="button" to="/">
        <span class="material-icons">article</span>
        <span class="text">About</span>
       </router-link>
       <router-link class="button" to="/">
        <span class="material-icons">groups</span>
        <span class="text">Team</span>
       </router-link>
       <router-link class="button" to="/">
        <span class="material-icons">contacts</span>
        <span class="text">Contact</span>
       </router-link>
       
    </div>

  </aside>
</template>

<style lang="scss" scoped>
aside {
  display: flex;
  flex-direction: column;
  padding: 1rem;
  width: calc(2rem + 32px);
  overflow: hidden;
  min-height: 100vh;

  background: var(--dark);
  color: var(--light);

  transition: all 0.3s ease-in-out;

  .logo {
    margin-bottom: 1rem;
    img {
      width: 2rem;
    }
  }
  h1,.button .text {
    opacity: 0;
    transition: all 0.3s ease-out;
  }

  .menu {
    margin: 0 -1rem;
    margin-top: 1rem;
    
    .button {
        display: flex;
        align-items: center;
        text-decoration: none;
        padding:  0.5rem 1rem;
        transition: all 0.3s ease-in-out;
        color: var(--light);
        gap: 0.5rem;
        font-size: 1.2rem;

    }
  }

  .menu-toggle-wrap {
    display: flex;
    justify-content: flex-end;
    margin-bottom: 1rem;
    position: relative;
    top: 0;
    transition: all 0.3s ease-in-out;

    .menu-toggle {
      transition: all 0.3s ease-in-out;

      .material-icons {
        color: var(--light);
        font-size: 2rem;
        transition: all 0.3s ease-in-out;
      }
      &:hover {
        .material-icons {
          color: var(--primary);
          transform: translateX(0.5rem);
        }

      }
    }
  }

  &.is_expanded {
    width: var(--sidebar-width);
    padding: 1rem 2rem;

    .menu-toggle-wrap {
      top: -3rem;
      .menu-toggle {
        transform: rotate(-180deg);
      }
    }
     h1,.button .text {
    opacity: 1;
  }

  }
  @media (max-width: 768px) {
    position: fixed;
    z-index: 999;
  }
}
</style>
