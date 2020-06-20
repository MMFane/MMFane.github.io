<template>
  <section id="router-view">
    <h1 id="title">Projects</h1>
    <ul id="thumbnails" v-if="selectedProject === null">
      <li v-for="(project, index) in projects" :key="index">
        <ProjectThumb
          :id="index"
          :img="project.img"
          :name="project.name"
          @changeProject="changeProject"
        />
      </li>
    </ul>
    <article id="project" v-else>
      <button @click="clearSelected">Back</button>
      This is Project {{ projects[selectedProject].name }}
    </article>
  </section>
</template>

<script>
import ProjectThumb from "@/components/ProjectThumbnail.vue";
import Projects from "@/assets/projects.json";

export default {
  name: "Home",
  components: {
    ProjectThumb,
  },
  data() {
    return {
      projects: Projects,
      selectedProject: null,
    };
  },
  methods: {
    changeProject(id) {
      console.log(`Home Changing Project to ${id}`);
      this.selectedProject = id;
    },
    clearSelected() {
      this.selectedProject = null;
    },
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

#thumbnails {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

#project {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
