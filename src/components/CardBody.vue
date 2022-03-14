<template>
	<ul>
		<li v-for="staff in refinedStaffArr" :key="staff">
			<div class="list-item-container">
				<p>{{ staff }}</p>
				<i class="fa fa-trash-o"></i>
			</div>
		</li>
	</ul>
</template>

<script>
export default {
	name: "CardBody",
	props: {
		staffNames: Array,
	},
	computed: {
		//to isolate names array and remove the first empty string in the names array
		refinedStaffArr() {
			return this.staffNames[0].data.slice(1);
		},
	},
};
</script>

<style scoped>
ul {
	position: relative;
	list-style-type: none;
	padding-inline-start: 0px;
	line-height: 5px;
	padding: 0px 5px 0px 5px;
}
.list-item-container {
	display: flex;
	align-items: center;
	flex-direction: row;
	justify-content: space-between;
}
li:after {
	content: "";
	width: 100%;
	border-bottom: solid 1px rgb(254, 250, 224, 0.3);
	position: absolute;
}
i {
	color: #e76f51;
	margin-left: 20px;
}
</style>
