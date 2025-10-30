<script>
	import projects from '$lib/Projects';
</script>

<svelte:head>
	<title>Sneha Sriram — Projects</title>
</svelte:head>

<div class="projectContainer">
	<div class="projects">
		<h1>Projects</h1>
		{#each projects as project}
			<div class="project">
				<div class="header">
					<h2>
						{project.title}
					</h2>
					 <div class="tags">
						{#each project.tags as tag}
							<span class="tag">{tag}</span>
						{/each}
					</div>
					<div class="techsContainer">
						Technologies:
						<div class="techs">
							{#each project.technologies as tech}
								<div>{tech}</div>
							{/each}
						</div>
					</div>
				</div>
				<p>
					{project.description}
				</p>
				<a href={project.url} target="_blank" rel="noreferrer">
					<div class="button">Project url =></div>
				</a>
			</div>
		{/each}
	</div>
</div>

<style>
	.tags {
        display: flex;
        gap: 0.5rem;
        margin-top: 0.5rem;
    }
    
    .tag {
        background-color: rgba(33, 170, 60, 0.68);
        padding: 0.2rem 0.8rem;
        border-radius: 1rem;
        font-size: 0.8rem;
        color: #ffffff;
    }

	.projectContainer {
		width: 100%;
		max-width: 900px;
		display: flex;
		justify-content: center;
		box-sizing: border-box;
		text-align: center;
		padding: 1em;
		margin: 0 auto;
		text-align: center;
	}

	.note {
		opacity: 0.5;
		margin: 0;
		max-width: 900px;
		text-align: left;
	}

	a {
		text-decoration: none;
	}

	.projectContainer .projects {
		display: grid;
		grid-template-columns: 1fr;
		grid-gap: 40px;
		margin-top: 30px;
	}

	h1 {
		font-weight: 700;
		text-align: start;
	}

	h2 {
		display: flex;
		margin: 0;
	}

	.project {
        text-align: start;
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        color: white;
        background: #111;
        padding: 2rem;
        width: 100%;
        border-radius: 25px;
        transition: transform 0.2s ease-in-out;
        height: 100%;
    }

	.project p {
		font-weight: 100;
		color: #708090;
	}

	.project:hover {
        transform: translateY(-5px);
    }

	.projects {
    width: 100%;
    margin: 50px auto;
    display: grid;
    grid-gap: 2rem;
    grid-template-columns: repeat(3, 1fr); /* Default to 3 columns */
    margin-bottom: 10px;
	}
	

	.techsContainer {
		display: flex;
		flex-wrap: wrap;
		gap: 10px;
	}

	.techs {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.techs > div {
		margin: 0 0 0 10px;
	}

	.button {
		display: flex;
		justify-content: center;
		align-items: center;
		color: white;
		border: 2px solid white;
		padding: 10px;
	}

		/* For tablets and smaller screens */
	@media (max-width: 1024px) {
		.projects {
			grid-template-columns: repeat(2, 1fr);
		}
	}

	/* For mobile screens */
	@media (max-width: 768px) {
		.projects {
			grid-template-columns: 1fr;
		}
	}
	
</style>
