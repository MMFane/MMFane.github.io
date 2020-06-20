<template>
  <nav>
    <p>Samantha Yeager, Front End Web Developer</p>
    <div>
      <router-link to="/">Projects</router-link> |
      <router-link to="/resume">Resume</router-link> |
      <router-link to="/about">About</router-link>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Nav",
};
</script>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
