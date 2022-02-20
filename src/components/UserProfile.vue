<template>
	<div class="card">
		<div class="card-body">
			<div class="center">
				<ProfilePicture :showStatus="false" :userData="userData" :classes="'margin-auto'"/>
				<h3>{{name}}</h3>
				<div class="status-display d-flex justify-content-center">
					<div :class="['status-circle align-self-center m-1', userData.status ? 'logged-in' : 'logged-out']"></div>
					<div>{{userData.status ? 'Online' : 'Offline'}}</div>
				</div>
				<div class="d-flex justify-content-center mt-5">
					<button type="button" class="btn btn-light border p-0 py-1 me-2">
						<img src="../assets/call.svg" class="" width="20%">
						<span class="thik ps-2">Call</span>
					</button>
					<button type="button" class="btn btn-light border p-0 py-1 ms-2">
						<!-- <img src="../assets/profile-avtar.svg" class=""  width="10%" height="100%"> -->
						<img src="../assets/call.svg" class="" width="20%">
						<span class="thik ps-2">Profile</span>
					</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import ProfilePicture from "./ProfilePicture.vue"
export default {
	name: "UserProfile",
	props: {
		userData: {
			Type: Object
		}
	},
	components: {
		ProfilePicture
	},
	computed: {
		name() {
			return this.userData.first_name + ((this.userData.first_name != "" && this.userData.last_name != "") ? " " : "") + this.userData.last_name
		}
	},
}
</script>

<style lang="scss" scoped>
.status-circle {
	width: 15px;
	height: 15px;
	border-radius: 50%;
	border: 1px solid rgb(34, 83, 26);
}
</style>