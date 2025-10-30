<script>
	import skills from '$lib/Skills';
</script>

<svelte:head>
	<title>Sneha Sriram — About</title>
</svelte:head>

<div class="container">
	<main>
		<h1>About</h1>
		<p>
			If you’ve taken the effort to stumble onto this page, I would be remiss not to introduce myself. Hi, I’m Sneha Sriram. Currently, I’m a 4th year at Wellesley College. Most of my interests are in CS and Ethics, and most of my work reflects that. I’m chronically obsessed with research, which reflects a lot about who I am as a person, and who I am as a thinker. In time, I hope to use that in tech for social good spaces. Welcome to my personal readme.
		</p>
		<h2>Skills</h2>
		{#each Object.entries(skills) as [section, technologies]}
			<ul>
				<li>
					<h4>
						{section}:
					</h4>
					<div class="list">
						{#each technologies as technology}
							<div>
								{technology}
							</div>
						{/each}
					</div>
				</li>
			</ul>
		{/each}
	</main>
</div>

<style>
	.container {
		max-width: 900px;
		padding: 0;
		display: flex;
		justify-content: center;
	}

	main {
		max-width: 100%;
		min-height: 500px;
		text-align: left;
		margin: 0 auto;
		box-sizing: border-box;
	}

	h1 {
		font-weight: 700;
		margin: 0 0 50px 0;
		font-size: 36px;
		text-align: start;
	}

	h2 {
		margin-top: 50px;
	}

	.list {
		display: flex;
		flex-direction: column;
		gap: 30px;
	}

	@media (min-width: 900px) {
		.list {
			flex-direction: row;
		}
		main > h1 {
			font-size: 48px;
		}
	}
</style>
