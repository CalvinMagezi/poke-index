<svelte:head>
	<title>About Svelte Kit Pokedex</title>
</svelte:head>

<div class="flex flex-col items-center space-y-6 justify-center h-full w-full">
	<a href="https://svelte.dev/">
		<img
			class="bg-orange-500 rounded-full p-2 shadow-lg shadow-orange-500 my-2 cursor-pointer hover:scale-110 transition duration-200 ease-in-out"
			src="/favicon.png"
			alt=""
		/>
	</a>

	<h1 class="font-bold text-3xl underline">About Svelte</h1>

	<div class="max-w-2xl mx-auto flex flex-col space-y-2">
		<p>
			Svelte is a radical new approach to building user interfaces. Whereas traditional frameworks
			like React and Vue do the bulk of their work in the browser, Svelte shifts that work into a
			compile step that happens when you build your app.
		</p>

		<p>
			Instead of using techniques like virtual DOM diffing, Svelte writes code that surgically
			updates the DOM when the state of your app changes.
		</p>

		<p>
			We're proud that Svelte was recently voted the most loved web framework with the most
			satisfied developers in a pair of industry surveys. We think you'll love it too. Read the
			introductory blog post to learn more.
		</p>
	</div>

	<h1 class="font-bold text-3xl underline">About Svelte Kit</h1>

	<div class="max-w-2xl mx-auto flex flex-col space-y-2">
		<p>
			SvelteKit is a framework for building web applications of all sizes, with a beautiful
			development experience and flexible filesystem-based routing.
		</p>

		<p>
			Unlike single-page apps, SvelteKit doesn't compromise on SEO, progressive enhancement or the
			initial load experience — but unlike traditional server-rendered apps, navigation is
			instantaneous for that app-like feel.
		</p>

		<p>Read the introductory blog post to learn more.</p>
	</div>
</div>
