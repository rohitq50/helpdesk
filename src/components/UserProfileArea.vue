<template>
	<div class="card">
		<div class="card-header p-0">
			<UserProfile :userData="thread"/>
		</div>
		<div class="card-body">
			<UserDetails :userData="thread"/>
		</div>
	</div>
</template>

<script>
import UserDetails from "./UserDetails.vue"
import UserProfile from "./UserProfile.vue"
export default {
	name: "UserProfileArea",
	props: {
		thread: {
			Type: Object
		}
	},
	components: {
		UserDetails,
		UserProfile
	}
}
</script>

<style lang="scss" scoped>
.card-body {
	background-color: #f0f0f5;
}
</style>