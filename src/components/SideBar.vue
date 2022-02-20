<template>
	<div class="sidebar d-flex flex-column justify-content-between">
		<div class="d-flex flex-column mb-3 center">
			<div @click="changService(0)" :class="['py-2 pointer', serviceType == 0 ? 'active' : '']">
				<img src='../assets/shareit.svg' class="svg-bg">
			</div>
			<div @click="changService(1)" :class="['py-2 pointer', serviceType == 1 ? 'active' : '']">
				<img src='../assets/inbox-solid.svg' class="svg-bg">
			</div>
			<div @click="changService(2)" :class="['py-2 pointer', serviceType == 2 ? 'active' : '']">
				<img src='../assets/user-group-solid.svg' class="svg-bg">
			</div>
			<div @click="changService(3)" :class="['py-2 pointer', serviceType == 3 ? 'active' : '']">
				<img src='../assets/chart-up.svg' class="svg-bg">
			</div>
		</div>
		<div class="mb-5">
			<ProfilePicture :userData="userData"/>
		</div>
	</div>
</template>

<script>
import ProfilePicture from "./ProfilePicture.vue"
export default {
	name: "SideBar",
	props: {
		userData: {
			Type: Object
		}
	},
	components: {
		ProfilePicture
	},
	data() {
		return {
			// svgNames: ["shareit", "inbox-solid", "user-group-solid", "chart-up"],
			serviceType: 1 // add meaningfull name
		}
	},
	methods: {
		changService(service) {
			this.serviceType = service
			this.$emit("serviceChnanged", service)
		}
	}
}
</script>

<style scoped lang="scss">
.sidebar {
	background-color:rgb(6, 70, 129);
	color: white;
	height:100vh;
}
.svg-bg {
	background-color:rgb(6, 70, 129);
	width: 50%;
}
.active {
	background-color:rgb(252, 252, 252) !important;
	color: rgb(6, 70, 129) !important;
}
</style>