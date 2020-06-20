<template>
  <section
    class="project"
    :style="{ backgroundImage: `url(${img})` }"
    @click="changeProject"
  >
    <p class="title">{{ name }}</p>
  </section>
</template>

<script>
export default {
  name: "Project",
  methods: {
    changeProject() {
      this.$emit("changeProject", this.name);
    },
  },
  props: {
    name: {
      type: String,
      default: "Project",
    },
    img: {
      type: String,
      default:
        "https://images.unsplash.com/photo-1499951360447-b19be8fe80f5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80",
    },
  },
};
</script>

<style>
.project {
  width: 300px;
  height: 300px;
  background-position: center;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  padding: 1rem;
  margin: 0 2rem 2rem 0;
}

.project .title {
  color: white;
  font-weight: bold;
  font-size: 2rem;
  background-color: rgba(0, 0, 0, 0.25);
  margin: 0;
  padding: 0.5rem 1rem;
}
</style>
