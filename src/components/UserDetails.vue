<template>
	<div class="card">
		<div class="card-body">
			<h5>Customer details</h5>
			<div class="d-flex justify-content-between">
				<span>Email</span>
				<span  class="thik">{{userData.email ? userData.email : '-'}}</span>
			</div>
			<div class="d-flex justify-content-between">
				<span>First Name</span>
				<span  class="thik">{{userData.first_name ? userData.first_name : '-'}}</span>
			</div>
			<div class="d-flex justify-content-between">
				<span>Last Name</span>
				<span class="thik">{{userData.last_name ? userData.last_name : '-'}}</span>
			</div>
			<div class="mt-2">
				<a href="#">View more details</a>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "UserDetails",
	props: {
		userData: {
			Type: Object
		}
	}
}
</script>

<style lang="scss" scoped>

</style>