<script>
  import { handle_promise } from "svelte/internal";


let handleClick = () => {
	color = (color == "black") ? "orange" : "black";
}
let handleInput = (e) => {
	color  = e.target.value;
}
let fname  = "Hoi"
let lname = "James"
let color = "black"
$: c = `${fname} ${lname} - ${color}`

$: {
	console.log(color)
}
</script>

<main>
	<h1>{c}</h1>
	<input type="text" bind:value={fname}>
	<input type="text" bind:value={lname}>
	<input type="text" bind:value={color}>
</main>


<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>