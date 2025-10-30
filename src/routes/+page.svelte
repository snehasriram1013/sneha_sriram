<script>
	import FaLinkedin from 'svelte-icons/fa/FaLinkedin.svelte';
	import FaGithub from 'svelte-icons/fa/FaGithub.svelte';
	import FaEnvelope from 'svelte-icons/fa/FaEnvelope.svelte';
	import FaMedium from 'svelte-icons/fa/FaMedium.svelte';
	import { modalOpened } from '$lib/store';
</script>

<svelte:head>
	<title>Sneha Sriram - Main page</title>
</svelte:head>
<main>
	<div class="container">
		<div class="intro-section">
			<div class="text-content">
			<div class="text-content">
				<h1 class="typing-text">Hi, I'm Sneha</h1>
			</div>
			<div class="headline">
				<p class="role">people centered developer and researcher</p>
				<p class="education">studying computer science + philosophy @ wellesley college</p>
				<p class="position">SERC Scholar @ MIT</p>
			</div>
			</div>
			<div class="image-content">
			<img src="src/lib/assets/sneha_nyc.jpg" alt="Sneha Sriram" />
			</div>
		</div>
	</div>
	<div class="icons">
		<div
			role="button"
			tabindex="0"
			on:keypress={() => {
				modalOpened.set(true);
			}}
			on:click={() => {
				modalOpened.set(true);
			}}
		>
			<div class="icon">
				<FaEnvelope />
			</div>
		</div>

		<a
			href="https://github.com/snehasriram1013"
			aria-label="GitHub"
			target="_blank"
			rel="noopener noreferrer"
		>
			<div class="icon">
				<FaGithub />
			</div>
		</a>
		<a
			href="https://www.linkedin.com/in/snehasriram/"
			aria-label="Linkedin"
			target="_blank"
			rel="noopener noreferrer"
		>
			<div class="icon">
				<FaLinkedin />
			</div>
		</a>
	</div>
</main>

<style>
	.container {
    width: 100%;
    max-width: 900px;
    margin: 0 auto;
    padding: 1em;
  }

  .intro-section {
    display: flex;
    align-items: center;
    gap: 2rem;
    margin: 2rem 0;
  }

  .image-content {
    flex-shrink: 0;
  }

  .image-content img {
    width: 200px;
    height: 200px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid white;
  }

  .typing-text {
    overflow: hidden;
    white-space: nowrap;
    border-right: 2px solid white;
    width: 0;
    animation: typing 2.2s steps(12) forwards,
               blink 0.8s infinite;
  }

  @keyframes typing {
    from { width: 0 }
    to { width: 100% }
  }

  @keyframes blink {
    50% { border-color: transparent }
  }

  @media (max-width: 768px) {
    .image-content img {
      width: 150px;
      height: 150px;
    }
  }
	a {
		color: white;
		text-decoration: none;
	}
	main {
		text-align: center;
		padding: 0;
		margin: 0 auto;
		text-align: center;

		display: flex;
		flex-direction: column;
		height: calc(100vh - 80px - 88px);
		justify-content: center;
		align-items: center;
	}

	h1 {
		font-weight: 700;
	}

	main > h1 {
		margin: 50px 10px 0;
		font-size: 36px;
	}

	.icons {
		display: flex !important;
		justify-content: center !important;
		align-items: center;
		gap: 20px;
		cursor: pointer;
		font-size: 30px;
		display: flex;
		justify-content: space-between;
		max-width: 200px;
		margin: 50px auto 0;
	}

	.icon {
		cursor: pointer;
		transition: color 0.2s ease-in-out;
		width: 40px;
	}
	.icon:hover {
		color: #ca3c25;
	}

	@media (min-width: 900px) {
		main > h1 {
			font-size: 48px;
		}
	}

	@media (min-width: 600px) {
		main {
			max-width: none;
		}
	}
</style>
