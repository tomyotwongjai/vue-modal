<!-- @format -->
// create slot for modal // create toggle to show and hide modal

<template>
	<h1>{{ title }}</h1>
	<p>Welcome...</p>

	<!-- Teleport  use for adding to different section in index.html -->
	<teleport to=".modals" v-if="showModal">
		<Modal theme="sale" @close="toggleShow">
			<template v-slot:links>
				<a href="#">Sign up</a>
				<a href="#">More info</a>
			</template>
			<h1>Hello</h1>
			<p>World</p>
		</Modal>
	</teleport>
	<button @click="toggleShow">Show Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
	components: { Modal },
	data() {
		return {
			title: "Hello Guys",
			showModal: false,
		};
	},
	methods: {
		toggleShow() {
			this.showModal = !this.showModal;
		},
	},
};
</script>

<style>
#app,
.modals {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	/* margin-top: 60px; */
}
h1 {
	border-bottom: 1px solid #ddd;
	display: inline-block;
	padding-bottom: 5px;
}

button {
	margin-top: 5px;
}
</style>
