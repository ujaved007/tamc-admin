<template>
	<button>{{ text }}</button>
</template>

<script>
export default {
	name: "Button",
	props: {
		text: String,
	},
};
</script>

<style scope>
button {
	background-color: #038e77;
	padding: 10px 15px 10px 15px;
	border-style: none;
	color: #fefae0;
	border-radius: 15px;
	font-size: 16px;
}
</style>
