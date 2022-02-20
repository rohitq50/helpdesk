<template>
	<div class="conversation-thread p-2">
		<div class="d-flex justify-content-md-between px-2">
			<input class="form-check-input align-self-center" type="checkbox" value="" id="flexCheckDefault">
			<div class="ps-3 flex-grow-1 align-self-start">
				<h6 class="mb-0">{{name}}</h6>
				<small class="">{{thread.type == 0 ? "Facebook DM" : "Facebook Post"}}</small>
			</div>
			<div class="align-self-start">{{thread.time}}</div>
		</div>
		<div class="p-2">
			<p class="msg-title mb-0">{{thread.title}}</p>
			<p class="mb-0 msg">{{msg}}</p>
		</div>
	</div>
</template>

<script>
export default {
	name: "ConversationThread",
	props: {
		thread: {
			Type: Object,
			required: true
		}
	},
	computed: {
		msg() {
			// TODO make substring dinamically
			return this.thread.msg.substring(0, 35) + "..."
		},
		name() {
			return this.thread.first_name + ((this.thread.first_name != "" && this.thread.last_name != "") ? " " : "") + this.thread.last_name
		}
	}
}
</script>

<style lang="scss" scoped>
.msg-title {
	font-weight: bold;
}
.icon-container {
	margin-left: none !important;
}
</style>