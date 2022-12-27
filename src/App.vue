<script setup>
import { RouterView } from 'vue-router'
</script>

<template>
	<div class="container">
		<RouterView />
	</div>
</template>

<style scoped>
.containter {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 0 20px;

}
</style>
