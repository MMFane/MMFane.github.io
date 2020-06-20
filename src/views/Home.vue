<template>
  <section id="router-view">
    <h1 id="title">Projects</h1>
    <ul id="projects">
      <li v-for="project in projects">
        <Project :name="project.name" :img="project.img" />
      </li>
    </ul>
  </section>
</template>

<script>
import Project from "@/components/Project.vue";
import Projects from "@/assets/projects.json";

export default {
  name: "Home",
  components: {
    Project,
  },
  data() {
    return {
      projects: Projects,
    };
  },
};
</script>

<style scoped>
ul {
  list-style: none;
}

#router-view #title {
  align-self: center;
}

#projects {
  display: flex;
  flex-wrap: wrap;
}
</style>
