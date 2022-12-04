<template>
    <div v-if="loading" class="text-center text-3xl">Loading...</div>
    <div class="text-center" v-for="project in projects" :key="project.objectId">
        <div class="b-red-300 p-6">
            <div class="project__name">
                <h2>{{ project.name }}</h2>
            </div>
            <div class="project__description">
                <p>{{ project.description }}</p>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    data() {
        return {
            projects: new Array(),
            loading: false
        }
    },
    methods: {
        fetchData() {
            this.loading = true;
            fetch("https://parseapi.back4app.com/classes/Project", {
                headers: {
                    "X-Parse-Application-Id": "yB953MbsVE0hvNYJLy9Udleb7uF0bwB4AWDoAuD9",
                    "X-Parse-REST-API-Key": "3TA8ugnSSIN1TB8tQNDGTudYk00i9dghfwloy84c"
                }
            }).then((response) => {
                return response.json();
            }).then((data) => {
                this.projects = data.results;
                this.loading = false;
            }).catch((error) => {
                this.loading = false;
                console.log(error);
            });
        }
    },
    mounted() {
        this.fetchData();
    }
};
</script>