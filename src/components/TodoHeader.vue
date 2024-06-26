<script setup></script>

<template>
  <header>
    <nav class="container">
      <div class="branding">
        <img
          src="../assets/marcille.png"
          alt="Marcille from Dungeon Meshi as the app logo"
        />
        <h1>Marcille's Todo App</h1>
      </div>
      <ul class="nav-routes">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
      </ul>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
  header {
    background-color: #4f7081;
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
