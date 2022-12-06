<script lang="ts">
import PageTitle from "../components/PageTitle.vue";
import ProjectsList from "../components/ProjectsList.vue";
import ProjectsArchieved from "../components/ProjectsArchieved.vue";
export default {
  components: {
    PageTitle,
    ProjectsList,
    ProjectsArchieved,
  },
};
</script>

<template>
  <PageTitle title="Projetos"></PageTitle>
  <div class="mt-6">
    <ProjectsList />
  </div>
  <div class="mt-6">
    <ProjectsArchieved />
  </div>
</template>
