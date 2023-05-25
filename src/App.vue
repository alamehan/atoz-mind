<script>
import Home from "./components/Home.vue";
import Example from "./components/example/container.vue";
import UserExperience from "./components/user-experience/container.vue";

// SETUP ROUTING (https://vuejs.org/guide/scaling-up/routing.html)
const routes = {
	"/": Home,
	"/example": Example,
	"/user-experience": UserExperience,
};

export default {
	data() {
		return {
			currentPath: window.location.hash,
		};
	},
	computed: {
		currentView() {
			return routes[this.currentPath.slice(1) || "/"] || NotFound;
		},
	},
	mounted() {
		window.addEventListener("hashchange", () => {
			this.currentPath = window.location.hash;
		});
	},
};
</script>

<template>
	<component :is="currentView" />
</template>

<style>
h1,
h2,
h3,
h4,
h5,
h6 {
	margin: 0;
}

h6 {
	font-weight: 400;
	line-height: 28px;
}
</style>
