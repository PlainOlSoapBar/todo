<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <header>
        <nav class="container">
            <div class="branding">
                <img src="../assets/marcille.png" alt="Marcille from Dungeon Meshi as the app logo" />
                <h1>Marcille's Todo App</h1>
            </div>
            <ul class="nav-routes">
                <RouterLink to="/">Home</RouterLink>
                <RouterLink to="/about">About</RouterLink>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
header {
  background-color: #4F7081;
  nav {
    display: flex;
    align-items: center;
    padding: 25px 16px;

    .branding {
      display: flex;
      align-items: center;
      gap: 8px;
      img {
        max-width: 50px;
      }

      h1 {
        font-size: 24px;
      }
    }

    .nav-routes {
      display: flex;
      flex: 1;
      justify-content: flex-end;
      gap: 12px;
      list-style: none;

      a {
        text-decoration: none;
        color: inherit;
      }
    }
  }
}
</style>