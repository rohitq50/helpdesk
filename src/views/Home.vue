<template>
	<div class="d-flex">
		<SideBar @changService="changService" :userData="userData" class="side"/>
		<ConversationArea @changeThread="changeThread" :selectedThread="selectedThread" :threads="threads" class="thread-area"/>
		<MsgArea :thread="threads[selectedThread]" class="msg-area"/>
		<UserProfileArea  :thread="threads[selectedThread]" class="profile-area"/>
	</div>
</template>

<script>
// @ is an alias to /src
import SideBar from '@/components/SideBar.vue'
import ConversationArea from '@/components/ConversationArea.vue'
import MsgArea from '@/components/MsgArea.vue'
import UserProfileArea from '@/components/UserProfileArea.vue'
export default {
	name: 'Home',
	components: {
		SideBar,
		ConversationArea,
		MsgArea,
		UserProfileArea
	},
	data() {
		return  {
			userData: {
				first_name: "Rohit",
				last_name: "Kumar",
				status: 1, //0 offline, 1 for online
				email: "rohit@richpannel.com",
			},
			threads: [
				{
					status: 1,
					email: "amit@richpannel.com",
					first_name: "Amit",
					last_name: "RG",
					type: 0,                 // 0 for DM, 1 for Post
					time: "10m",  // should be calculated
					title: "Awesome Product",
					msg: "Hey There! I probably did one of the best",
					msgs: [
						{
							msg_id: 1,
							is_sending: 0, // 0 for recieving 1 for sending
							sender_id: 22,
							sender_image: "img url",
							sender_name: "Amit RG",
							time: "Mar 05, 2:22 AM",
							text: "Is it in stock right now?",
						},
						{
							msg_id: 2,
							is_sending: 1, // 0 for recieving 1 for sending
							sender_id: 11,
							sender_image: "img url",
							sender_name: "Richard Panel",
							time: "Mar 05, 2:22 AM",
							text: "We've 3 left in stock!",
						},
						{
							msg_id: 2,
							is_sending: 1, // 0 for recieving 1 for sending
							sender_id: 11,
							sender_image: "img url",
							sender_name: "Richard Panel",
							time: "Mar 05, 2:22 AM",
							text: "If you order before 8PM we can ship it today.",
						}
					]
				},
				{
					email: "hitensaxena@richpannel.com",
					status: 0, //0 offline, 1 for online
					first_name: "Hiten",
					last_name: "Saxena",
					type: 1,                 // 0 for DM, 1 for Post
					time: "10m",  // should be calculated
					title: "Available in store?",
					msg: "Hi do you have any T-Shirt available in store",
					msgs: [
						{
							msg_id: 1,
							is_sending: 0, // 0 for recieving 1 for sending
							sender_id: 22,
							sender_image: "img url",
							sender_name: "Amit RG",
							time: "Mar 05, 2:22 AM",
							text: "Is it in stock right now?",
						},
						{
							msg_id: 2,
							is_sending: 1, // 0 for recieving 1 for sending
							sender_id: 11,
							sender_image: "img url",
							sender_name: "Richard Panel",
							time: "Mar 05, 2:22 AM",
							text: "We've 3 left in stock!",
						},
						{
							msg_id: 2,
							is_sending: 1, // 0 for recieving 1 for sending
							sender_id: 11,
							sender_image: "img url",
							sender_name: "Richard Panel",
							time: "Mar 05, 2:22 AM",
							text: "If you order before 8PM we can ship it today.",
						}
					]
				}
			],
			selectedThread: 0
		}
	},
	methods: {
		changService() {

		},
		changeThread(threadIndex) {
			this.selectedThread = threadIndex
		}
	}
}
</script>

<style lang="scss" scoped>
.side {
	width: 5%;
}
.thread-area {
	width: 20%;
}
.msg-area {
	width: 50%;
}
.profile-area {
	width: 25%;
}
</style>
