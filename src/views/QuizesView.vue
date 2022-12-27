<script setup>
import data from '../data/quizes.json'
import { ref, watch } from 'vue'
import Card from '../components/Card.vue'

const quizes = ref(data)
const search = ref('')

watch(search, () => {
	quizes.value = data.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})
</script>

<template>
	<div class="containter">
		<header>
			<h1>Quizzz</h1>
			<input v-model.trim="search" type="text" placeholder="Search..." />
		</header>
		<div class="options-container">
			<Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
		</div>
	</div>
</template>

<style scoped>

.header {
	display: flex;
	align-items: center;
	margin-bottom: 10px;
	margin-top: 10px;
}

header h1 {
	margin-right: 30px;
	font-weight: bold;
}

header input {
	padding: 5px;
	border: none;
	background-color: rgb(78, 78, 78);
	border-radius: 5px;
	color: white;
}

.options-container {
	display: flex;
	flex-wrap: wrap;
	margin-top: 40px;
}
</style>
