<template>
	<form action="">
		<search-bar />
		<card-button text="Add" />
	</form>
</template>

<script>
import SearchBar from "./SearchBar.vue";
import CardButton from "./CardButton.vue";

export default {
	name: "AddGuard",
	components: {
		SearchBar,
		CardButton,
	},
};
</script>

<style scope>
form {
	display: grid;
	grid-template-columns: 1fr 0.2fr;
	grid-gap: 20px;
}
</style>
