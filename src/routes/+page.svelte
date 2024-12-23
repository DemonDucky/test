<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';

	const subheadlines = [
		'Crafting Exceptional Brands, Powerful Web Experiences, and Scalable SaaS Solutions.',
		'Transforming Ideas into Market-Leading Products.',
		'Where Marketing, Design, and Technology Converge to Create Unforgettable Experiences.'
	];

	const services = [
		{
			title: 'Web Development Mastery',
			description:
				'I build responsive, fast-loading websites using SvelteKit, optimized for user engagement and SEO.'
		},
		{
			title: 'SEO & Marketing Alchemy',
			description:
				'Implementing cutting-edge SEO strategies and digital marketing techniques to drive traffic and sales.'
		},
		{
			title: 'SaaS Development for the Elite',
			description: 'Creating scalable SaaS solutions that empower businesses to innovate and grow.'
		}
	];

	const projects = [
		{
			title: 'Amorees',
			description:
				"Amorees is a beaded jewelry brand, but it not just a fashion brand, it's also the mix of fashion & technology.",
			img: '/images/chopard.png',
			link: '/projects/amorees'
		}
	];

	const skills = [
		'Frontend Development',
		'UI/UX Design',
		'Social Media Marketing',
		'SEO Optimization',
		'Content Marketing',
		'Cold Email'
	];

	let currentSubheadline = 0;

	onMount(() => {
		const interval = setInterval(() => {
			currentSubheadline = (currentSubheadline + 1) % subheadlines.length;
		}, 5000);

		return () => {
			clearInterval(interval);
		};
	});
</script>

<svelte:head>
	<title>LUONG TUAN ANH - PORTFOLIO</title>
</svelte:head>

<section
	id="hero"
	class="flex relative flex-col justify-center items-center bg-gradient-to-br min-h-dvh from-primary/10 to-secondary/10"
>
	<div class="container px-4 mx-auto text-center">
		<h1 class="mb-8 text-lg font-bold text-gray-800 md:text-6xl">
			Redefining Digital Mastery, One Pixel at a Time
		</h1>
		<p class="mb-8 h-20 text-xl text-gray-600 md:text-2xl">
			{subheadlines[currentSubheadline]}
		</p>
		<div class="flex flex-col gap-4 justify-center sm:flex-row">
			<Button class="font-bold" size="lg">Start Your Digital Journey</Button>
			<Button size="lg" variant="outline">View My Work</Button>
		</div>
	</div>
</section>

<section id="about" class="py-20 bg-white">
	<div class="container px-4 mx-auto">
		<h2 class="mb-8 text-3xl font-bold text-center text-gray-800 md:text-4xl">
			A Visionary at the Intersection of Art and Technology
		</h2>
		<p class="mx-auto mb-8 max-w-3xl text-lg text-center text-gray-600">
			My journey began in the digital marketing world, where I discovered the power of storytelling
			and learned how to craft compelling brand experiences. Over time, I transitioned to designing
			websites and SaaS solutions, blending design sensibilities with strong technical skills.
			Today, I focus on creating digital experiences that not only engage users but also drive
			business results.
		</p>
		<blockquote class="mb-12 text-2xl italic font-bold text-center text-primary">
			"I don't just build websites. I build the future."
		</blockquote>
		<div class="flex flex-wrap gap-4 justify-center">
			{#each skills as skill}
				<span class="px-4 py-2 text-sm font-medium text-gray-800 bg-gray-100 rounded-full"
					>{skill}</span
				>
			{/each}
		</div>
	</div>
</section>

<!-- <section id="projects" class="py-20 bg-white">
	<div class="container px-4 mx-auto">
		<h2 class="mb-12 text-3xl font-bold text-center text-gray-800 md:text-4xl">
			Crafted with Precision, Built to Endure
		</h2>
		<div class="px-2 mx-auto max-w-screen-7xl xl:px-12">
			{#each projects as project}
				<div class="p-6 w-full text-center bg-gray-50 rounded-lg shadow-md">
					<h3 class="mb-4 text-4xl font-bold text-gray-800">{project.title}</h3>
					<p class="mb-6 text-gray-600">{project.description}</p>
					<img src={project.img} alt={project.title} class="w-full h-auto rounded-lg" />
					<a href={project.link} class="font-medium text-primary hover:underline">View Project →</a>
				</div>
			{/each}
		</div>
	</div>
</section> -->

<section id="services" class="py-20 bg-white">
	<div class="container px-4 mx-auto">
		<h2 class="mb-12 text-3xl font-bold text-center text-gray-800 md:text-4xl">
			Digital Solutions That Set Your Brand Apart
		</h2>
		<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
			{#each services as service}
				<article class="p-6 bg-white rounded-lg shadow-md transition-transform hover:scale-105">
					<h3 class="mb-4 text-xl font-bold text-gray-800">{service.title}</h3>
					<p class="mb-6 text-gray-600">{service.description}</p>
					<Button variant="outline">Learn More</Button>
				</article>
			{/each}
		</div>
	</div>
</section>

<section id="contact" class="py-20 bg-white">
	<div class="container px-4 mx-auto">
		<h2 class="mb-12 text-3xl font-bold text-center text-gray-800 md:text-4xl">Get in Touch</h2>
		<form class="p-8 mx-auto max-w-lg bg-white rounded-lg shadow-md">
			<div class="mb-6">
				<label for="name" class="block mb-2 font-medium text-gray-700">Name</label>
				<input
					type="text"
					id="name"
					name="name"
					required
					placeholder="Enter your name"
					class="px-4 py-2 w-full rounded-md border border-gray-300 focus:outline-none focus:ring-2 focus:ring-primary"
				/>
			</div>
			<div class="mb-6">
				<label for="email" class="block mb-2 font-medium text-gray-700">Email</label>
				<input
					type="email"
					id="email"
					name="email"
					required
					placeholder="Enter your email"
					class="px-4 py-2 w-full rounded-md border border-gray-300 focus:outline-none focus:ring-2 focus:ring-primary"
				/>
			</div>
			<div class="mb-6">
				<label for="message" class="block mb-2 font-medium text-gray-700">Message</label>
				<textarea
					id="message"
					name="message"
					required
					placeholder="Your message"
					class="px-4 py-2 w-full h-32 rounded-md border border-gray-300 resize-none focus:outline-none focus:ring-2 focus:ring-primary"
				></textarea>
			</div>
			<Button type="submit" class="w-full">Send Message</Button>
		</form>
	</div>
</section>
