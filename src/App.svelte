<script>
  import { handle_promise } from "svelte/internal";

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

</script>

<main>
 {#each blogs as blog (blog.id)}
  <div>
	{blog.id}
	<p>{blog.title}</p>
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