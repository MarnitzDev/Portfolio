<script>
  import { fade } from 'svelte/transition';

  // Sample project data - replace with your actual projects
  const projects = [
    {
      id: 1,
      title: "E-commerce Platform",
      description: "A full-stack e-commerce solution built with SvelteKit and Stripe integration.",
      technologies: ["SvelteKit", "Node.js", "PostgreSQL", "Stripe"],
      imageUrl: "/images/ecommerce-project.jpg",
      githubUrl: "https://github.com/yourusername/ecommerce-project",
      liveUrl: "https://ecommerce-project.com"
    },
    {
      id: 2,
      title: "Weather Dashboard",
      description: "A responsive weather application using OpenWeatherMap API and Svelte.",
      technologies: ["Svelte", "OpenWeatherMap API", "Chart.js"],
      imageUrl: "/images/weather-dashboard.jpg",
      githubUrl: "https://github.com/yourusername/weather-dashboard",
      liveUrl: "https://weather-dashboard-demo.com"
    },
    // Add more projects as needed
  ];
</script>

<svelte:head>
  <title>My Projects | Developer Portfolio</title>
</svelte:head>

<div class="max-w-4xl mx-auto">
  <h1 class="text-4xl font-bold mb-8">My Projects</h1>

  <div class="space-y-12">
    {#each projects as project (project.id)}
      <div class="bg-white shadow-lg rounded-lg overflow-hidden" transition:fade>
        <img src={project.imageUrl} alt={project.title} class="w-full h-64 object-cover" />
        <div class="p-6">
          <h2 class="text-2xl font-semibold mb-2">{project.title}</h2>
          <p class="text-gray-600 mb-4">{project.description}</p>
          <div class="mb-4">
            <h3 class="text-lg font-semibold mb-2">Technologies Used:</h3>
            <div class="flex flex-wrap gap-2">
              {#each project.technologies as tech}
                <span class="bg-blue-100 text-blue-800 px-2 py-1 rounded text-sm">{tech}</span>
              {/each}
            </div>
          </div>
          <div class="flex space-x-4">
            <a href={project.githubUrl} target="_blank" rel="noopener noreferrer" class="bg-gray-800 hover:bg-gray-700 text-white px-4 py-2 rounded">
              GitHub Repo
            </a>
            <a href={project.liveUrl} target="_blank" rel="noopener noreferrer" class="bg-blue-600 hover:bg-blue-500 text-white px-4 py-2 rounded">
              Live Demo
            </a>
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>