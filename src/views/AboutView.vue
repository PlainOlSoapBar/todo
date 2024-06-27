<template>
  <main>
    <h1>About this app</h1>
    <p class="about-paragraph-1">
      <span
        >This is a simple todo app built with Vue 3 and the Composition API
        (Reactivity API).</span
      >
    </p>
    <p class="about-paragraph-2">
      <span>
        This app is based off of the
        <a href="https://www.youtube.com/watch?v=KTFH4P8unUQ"
          >Vue 3 Crash Course | Project From Scratch</a
        >
        by
        <a href="https://www.youtube.com/@JohnKomarnicki">John Komarnicki</a>.
      </span>
    </p>
  </main>
</template>

<style scoped lang="scss">
  main {
    display: flex;
    flex-direction: column;
    max-width: 800px;
    width: 100%;
    margin: 0 auto;
    padding: 40px 16px;

    h1 {
      margin-bottom: 16px;
      text-align: center;
    }

    .about-paragraph-1 {
      display: flex;
      flex-direction: column;
      list-style: none;
      gap: 20px;
    }

    .about-paragraph-2 {
      display: flex;
      flex-direction: column;
      list-style: none;
      margin-top: 24px;
      gap: 20px;
    }
  }
</style>
