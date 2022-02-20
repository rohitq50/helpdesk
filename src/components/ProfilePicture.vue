<template>
	<div :class="['icon-container', classes]">
		<img src="../../public/assets/tiger.jpg" id="profile-img" class="profile-picture circle user-avatar">
		<div v-if="showStatus" :class="['status-circle', userData.status ? 'logged-in' : 'logged-out']"></div>
	</div>
</template>

<script>
export default {
	name: "ProfilePicture",
	props: {
		imgurl: {
			default: "../../public/assets/tiger.jpg"
		},
		width: {
			default: "60%"
		},
		height: {
			default: "30%"
		},
		userData: {
			Type: Object
		},
		showStatus: {
			default: true
		},
		classes: {
			default: "margin-auto"
		}
	}
}
</script>

<style scoped>
.icon-container {
	width: 50px;
	height: 50px;
	position: relative;
	display: block;
}
img {
	height: 100%;
	width: 100%;
	border-radius: 50%;
}
.status-circle {
	width: 15px;
	height: 15px;
	border-radius: 50%;
	border: 1px solid rgb(34, 83, 26);
	bottom: 0;
	right: 0;
	position: absolute;
}
</style>