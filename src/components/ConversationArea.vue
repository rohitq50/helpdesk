<template>
	<div class="card">
		<div class="card-header px-1">
			<div class="d-flex justify-content-md-between align-items-center">
				<img src="../assets/hamburger.svg" width="10%">
				<h3 class="ps-1 flex-grow-1">Conversations</h3>
				<img class="refresh" src="../assets/refresh.svg" width="10%">
			</div>
		</div>
		<div class="card-body p-0">
			<div @click="selectThread(index)" v-for="(thread, index) in threads" :key="index">
				<ConversationThread :thread="thread" :class="selectedThread == index ? 'active' : ''"/>
			</div>
		</div>
	</div>
</template>

<script>
import ConversationThread from "./ConversationThread.vue"
export default {
	name: "ConversationArea",
	props: {
		threads: {
			Type: Array
		},
		selectedThread: {
			default: 0
		}
	},
	components: {
		ConversationThread
	},
	methods: {
		selectThread(threadIndex) {
			this.selectedThread = threadIndex
			this.$emit("changeThread", threadIndex)
		}
	}
}
</script>

<style lang="scss" scoped>
.active {
	background-color: rgb(232, 232, 233);
}

</style>