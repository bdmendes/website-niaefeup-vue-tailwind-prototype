<template>
  <div class="text-center">
    <h1 class="text-2xl font-bold">&#60; Projetos Arquivados /></h1>
  </div>
  <ul class="grid grid-cols-3 align-items-center gap-3 pt-10">
    <li class="text-center   bg-white border
       border-red-200 rounded-lg shadow-md dark:bg-red-800 dark:border-red-700" 
       v-for="project in projects.slice(0, 1)"
      :key="project.objectId">
      <div class="flex justify-center align-items-center pt-10 ">
        <img class="project_image rounded-t-lg w-1/5" :src="project.imageURL" />
      </div>
      <div class="project__description mb-3 font-normal text-gray-700 dark:text-gray-400 pt-8">
        <p>{{ project.description }}</p>
      </div>
    </li>
    <li class="text-center   bg-white border
       border-red-200 rounded-lg shadow-md dark:bg-red-800 dark:border-red-700" 
       v-for="project in projects.slice(1, 3)"
      :key="project.objectId">
      <div class="flex justify-center align-items-center pt-10 ">
        <img class="project_image rounded-t-lg w-1/2" :src="project.imageURL" />
      </div>
      <div class="project__description mb-3 font-normal text-gray-700 dark:text-gray-400 pt-10">
        <p>{{ project.description }}</p>
      </div>
    </li>
  </ul>
</template>

<script lang="ts">
export default {
  data() {
    return {
      projects: new Array(),
      loading: false,
    };
  },
  methods: {
    fetchData() {
      this.loading = true;
      fetch("https://parseapi.back4app.com/classes/Project", {
        headers: {
          "X-Parse-Application-Id": "yB953MbsVE0hvNYJLy9Udleb7uF0bwB4AWDoAuD9",
          "X-Parse-REST-API-Key": "3TA8ugnSSIN1TB8tQNDGTudYk00i9dghfwloy84c",
        },
      })
        .then((response) => {
          return response.json();
        })
        .then((data) => {
          this.projects = data.results;
          this.loading = false;
        })
        .catch((error) => {
          this.loading = false;
          console.log(error);
        });
    },
  },
  mounted() {
    this.fetchData();
  },
};
</script>