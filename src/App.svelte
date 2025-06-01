<script>
  import { handle_promise } from "svelte/internal";

  import Modal from "./Modal.svelte"

let blogs = [
	{
		id: 1,
		title: 'My First Blog',
		body: 'Lorem ipsum dolor sit amet consectetur',
		likes: 30
	},
	{
		id: 2,
		title: 'Opening Party!',
		body: 'Why do we use it? It is a long established fact',
		likes: 20
	},
	{
		id: 3,
		title: 'Dev Meetup',
		body: 'There are many variations of passages',
		likes: 15
	}
];

const deleteBlog = (id) => {
	console.log(id)
	blogs = blogs.filter((blog) => blog.id !== id)
}
$: num = blogs.length;

</script>
<Modal/>
<main>
	{#if num === 3}
	<p>3</p>
	{:else if num === 2}
	 <p>2</p>
	{:else if num === 1}
	 <p>1</p>
	{:else}
	<p>dead</p>
	{/if}

 {#each blogs as blog (blog.id)}
  <div>
	{blog.id}
	<p>{blog.title}</p>
	{#if blog.likes === 20}
	<p>omg	</p>
	{/if}
	<button on:click={() => {deleteBlog(blog.id)}}>delete blog</button>

  </div>
  {:else}
  	<p>no item to show</p>
 {/each}
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