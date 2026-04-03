<script>
	const scrolls = Array.from({ length: 500 });
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" />
<link
	href="https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200..1000;1,200..1000&display=swap"
	rel="stylesheet"
/>

<div class="centerdiv">
	{#each scrolls as scroll}
		<h1>Scroll down!</h1>
	{/each}
	<div class="divider"></div>

	<h1>Nope.</h1>
	<a href="/premium" class="clear">Back to start</a>
</div>
