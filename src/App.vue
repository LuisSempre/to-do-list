<template>
	<div id="app">
		<h1>To do list</h1>
		<TaskGrid :tasks="tasks"/>
	</div>
</template>

<script>
import TaskGrid  from './components/TaskGrid';

export default {
	components: { TaskGrid },
	data () {
		return {
			tasks: [
				{ name: 'Lavar roupa', pending: false},
				{ name: 'Comprar blusa', pending: true}
			]
		}
	}
}
</script>

<style>
	body {
		font-family: 'Roboto', sans-serif;
		background: black;
		color: #FFF;
	}

	#app {
		display: flex;
		flex: 1;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
	}

	#app h1 {
		margin-bottom: 5px;
		font-weight: 300;
		font-size: 3rem;
	}
</style>
