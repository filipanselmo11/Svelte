<script>
	import { onMount } from "svelte";
	import axios from "axios";

	const endpoint = "https://jsonplaceholder.typicode.com/posts";

	let posts = [];

	onMount(async function () {
		try {
			const response = await axios.get(endpoint);
			console.log(response.data);
			posts = response.data;
		} catch (erro) {
			console.log(erro);
		}
	});
	/*onMount(async function(){
		axios.all([
			axios.get("https://jsonplaceholder.typicode.com/posts"),
			axios.get("https://jsonplaceholder.typicode.com/comments"),
		])
		.then((responseArr) => {
			console.log("First Post: ", responseArr[0].data[0].title);
			console.log("Second Comment: ", responseArr[1].data[1].body);
		})
		.catch((erro) => {
			console.log(erro);
		});
	});*/
</script>

<main>
	{#each posts as article}
		<div>
			<p>{article.title}</p>
		</div>
	{/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
