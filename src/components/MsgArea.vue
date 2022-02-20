<template>
	<div class="card">
		<div class="card-header">
			<div class="">
				<h3 class="ps-3">{{name}}</h3>
			</div>
		</div>
		<div class="card-body p-0 d-flex flex-column justify-content-between">
			<div>
				<div @click="threadClicked = index" v-for="(msg, index) in thread.msgs" :key="index">
					<MsgThread :isSameThread="isSameThread(msg, index)" :msg="msg" :class="threadClicked == index ? 'active' : ''" :classes="(index == 0)? 'pt-3': ''"/>
				</div>
			</div>
			<div class="m-3">
				<input type="text" class="form-control" id="send-msg-field" :placeholder="placeholderMsg">
			</div>
		</div>
	</div>
</template>

<script>
import MsgThread from "./MsgThread.vue"
export default {
	name: "ChatArea",
	props: {
		thread: {
			Type: Object
		}
	},
	components: {
		MsgThread
	},
	data() {
		return {
			threadClicked: 0,
			lastUser: null,
			recentTime: null,
			sameThread: true
		}
	},
	computed: {
		placeholderMsg() {
			return `Message ${this.thread.name}`
		},
		name() {
			return this.thread.first_name + ((this.thread.first_name != "" && this.thread.last_name != "") ? " " : "") + this.thread.last_name
		}
	},
	methods: {
		isSameThread(msg, index) {
			if(this.lastUser === null) {
				this.lastUser = msg.sender_id
			}
			if(this.recentTime === null) {
				this.recentTime = msg.time
			}
			let totalLenght = this.thread.msgs.length
			if(totalLenght == index + 1) {
				this.sameThread = false;
				return false;
			}
			let nextThread =  this.thread.msgs[index + 1]

			if(msg.sender_id == nextThread.sender_id && true) { //(msg.time - this.recentTime) > 0
				this.sameThread = true;
				return true;

			}
			this.sameThread = false;
			return false
		}
	}
}
</script>

<style lang="scss" scoped>
.card-body {
	background-color: #f3f3f3;
}
</style>