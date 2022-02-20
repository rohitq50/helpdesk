<template>
	<div :class="['d-flex', msg.is_sending ? 'justify-content-end' : 'justify-content-start', classes]">
		<div :class="['msg-display-area d-flex px-3', msg.is_sending ? 'flex-row-reverse' : 'flex-row']">
			<div class="d-flex flex-column">
				<ProfilePicture :showStatus="false" :classes="''"/>
				<div></div>
			</div>
			<div class="px-2">
				<p class="mb-0 p-2 msg-thread">{{msg.text}}</p>
				<div v-if=" ! isSameThread" :class="['msg-details-area d-flex pb-3',  msg.is_sending ? 'justify-content-end' : 'justify-content-start']">
					<small>{{msg.sender_name}}</small>
					-
					<small>{{msg.time}}</small>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import ProfilePicture from "./ProfilePicture.vue"
export default {
	name: "MsgThread",
	props: {
		msg: {
			Type: Object
		},
		isSameThread: {
			default: false
		},
		classes: {
			default: ""
		}
	},
	components: {
		ProfilePicture
	}
}
</script>

<style lang="scss" scoped>
.msg-thread {
	background-color: white;
	// border: 1px solid rgb(190, 185, 185);
	border-radius: 5px;
}
</style>