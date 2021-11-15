<template>
	<h1>{{ title }}</h1>
	<input type="text" id="inputField" class="inputField"/>
	<button @click="addToDoItem" id="addToDo" class="addToDo">Add Item</button>
	<ul class="results" id="results">

	</ul>
</template>

<script>
export default {
  name: 'App',
	data() {
		return {
			title: 'To-Do App',
		}
	},
	methods: {
		addToDoItem() {
			let input = document.getElementById('inputField');
			let newElement = document.createElement('li');
			let results = document.getElementById('results');

			if(input.value) {
				newElement.innerText = input.value;
				results.appendChild(newElement);
				input.value = '';

				newElement.addEventListener('click', function() {
					results.removeChild(newElement);
				})
			} else {
				alert('Please enter some text');
			}
		}
	}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.inputField {
	font-size: 2rem;
	margin-right: 1rem;
}

.addToDo {
	height: 2rem;
}

.results li {
	list-style-type: none;
}

.results li:hover{
	color: red;
}

</style>
