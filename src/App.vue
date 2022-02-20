<template>
	<div id="app">
		<Home />
		<!-- <router-view/> -->
	</div>
</template>

<script>
import Home from "@/views/Home.vue";
export default {
	components: {
		Home
	}
}
</script>

<style lang="scss">
p {
  font-size: 2vmin;
}
.center {
	text-align: center;
}
.pointer {
	cursor: pointer;
}
.margin-auto {
	margin-left: auto;
    margin-right: auto;
}
.logged-in {
    background-color: green;
}
.logged-out {
   background-color: grey;
}
.thik {
	font-weight: bold;
}
</style>
