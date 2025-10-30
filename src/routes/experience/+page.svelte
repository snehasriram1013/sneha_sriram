<script>
  import experiences from '$lib/Experiences';
  import leadership from '$lib/leadership';
</script>

<svelte:head>
  <title>Sneha Sriram — Experience</title>
</svelte:head>

<div class="experience-container">
  <section>
    <h1>Experience</h1>
    {#each experiences as exp}
      <div class="experience-card">
        <div class="header">
          <h2><strong>{exp.company}</strong> | <em>{exp.role}</em></h2>
          <div class="subheader">
            <span class="location">{exp.location}</span>
            <span class="date">{exp.date}</span>
          </div>
        </div>
        <ul>
          {#each exp.points as point}
            <li>{point}</li>
          {/each}
        </ul>
      </div>
    {/each}
  </section>

  <section>
    <h1>Leadership</h1>
    {#each leadership as lead}
      <div class="experience-card">
        <div class="header">
          <h2><strong>{lead.organization}</strong> | <em>{lead.role}</em></h2>
          <div class="subheader">
            <span class="date">{lead.date}</span>
          </div>
        </div>
      </div>
    {/each}
  </section>
</div>

<style>
  .experience-container {
    max-width: 900px;
    margin: 0 auto;
    padding: 2rem;
  }

  .experience-card {
    margin-bottom: 3rem;
    padding: 0;
    transition: transform 0.2s ease-in-out;
  }

  .header {
    margin-bottom: 1rem;
  }

  .subheader {
    display: flex;
    justify-content: space-between;
    color: #708090;
    margin: 0.5rem 0;
    font-size: 0.9rem;
  }

  h1 {
    margin-bottom: 2rem;
    font-weight: 700;
    text-align: left;
  }

  h2 {
    font-size: 1.2rem;
    margin: 0;
    color: #ffffff;
  }

  ul {
    list-style-type: disc;
    margin-left: 1.5rem;
    color: #708090;
  }

  li {
    margin-bottom: 0.5rem;
    line-height: 1.5;
  }

  @media (max-width: 768px) {
    .subheader {
      flex-direction: column;
      gap: 0.25rem;
    }
  }

  section {
    margin-bottom: 4rem;
  }

  section:last-child {
    margin-bottom: 0;
  }
</style>