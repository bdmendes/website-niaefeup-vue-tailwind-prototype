<template>
  <div v-if="loading" class="text-center text-3xl">Loading...</div>
  <ul class="grid grid-cols-2 gap-4 justify-items-center">
    <li
      class="text-center row-start-1 row-span-2 w-7/12 col-start-2 bg-white border
       border-red-200 rounded-lg shadow-md dark:bg-red-800 dark:border-red-700"
      v-for="project in projects.slice(0, 1)"
      :key="project.objectId"
    >
    <div class="flex justify-center">
        <img class="project_image rounded-t-lg h-1/2 w-1/4 pt-10" :src="project.imageURL" />
    </div>
      <div
        class="project__description mb-3 font-normal text-gray-700 dark:text-gray-400 pt-10"
      >
        <p>{{ project.description }}</p>
      </div>
    </li>
    <li
      class="text-center bg-white border border-red-200 rounded-lg shadow-md dark:bg-red-800 w-7/12 dark:border-red-700"
      v-for="project in projects.slice(1, 2)"
      :key="project.objectId"
    >
      <div class="flex justify-center">
        <img class="project_image rounded-t-lg w-1/2 pt-5" :src="project.imageURL" />
      </div>
      <div
        class="project__description mb-3 font-normal text-gray-700 dark:text-gray-400"
      >
        <p>{{ project.description }}</p>
      </div>
    </li>
    <li
      class="text-center bg-white border border-red-200 rounded-lg shadow-md dark:bg-red-800 w-7/12 dark:border-red-700"
      v-for="project in projects.slice(2, 3)"
      :key="project.objectId"
    >
        <div class="flex justify-center">
        <img class="project_image rounded-t-lg w-1/2 pt-5" :src="project.imageURL" />
        </div>
      <div
        class="project__description mb-3 font-normal text-gray-700 dark:text-gray-400"
      >
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
