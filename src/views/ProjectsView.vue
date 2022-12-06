<script lang="ts">
import PageTitle from "../components/PageTitle.vue";
import ProjectsList from "../components/ProjectsList.vue";

export default {
  components: {
    PageTitle,
    ProjectsList,
  },
};
</script>

<template>
  <PageTitle title="Projetos"></PageTitle>
  <div class="mt-6">
    <ProjectsList />
  </div>
</template>
