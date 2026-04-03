<script>
	//@ts-nocheck
	const totalClicks = 5;
	let clicks = $state(totalClicks);

	function subtract() {
		clicks -= 1;
	}
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" />
<link
	href="https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200..1000;1,200..1000&display=swap"
	rel="stylesheet"
/>

{#if clicks > 0}
	<div class="centerdiv">
		<h1>You need premium to do that!</h1>
		{#if clicks == totalClicks}
			<button onclick={subtract}>Get premium</button>
		{:else}
			<button onclick={subtract}>Are you sure?</button>
			<p>Clicks remaining: {clicks}</p>
		{/if}
	</div>
{:else}
	<div class="fullcenterdiv">
		<h1>You need at least a Premium+ subscription to get premium</h1>

		<a href="/no" class="clear">Get Premium+</a>
	</div>
{/if}
