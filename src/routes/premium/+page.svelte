<script>
	//@ts-nocheck
	const totalClicks = 100;
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
		<div class="divider"></div>
		{#if clicks == totalClicks}
			<button class="clear" onclick={subtract}>Get premium</button>
			<button class="clear" onclick={subtract}>Get premium?</button>
			<button class="clear" onclick={subtract}>Get premium??</button>
			<div class="divider"></div>
			<button onclick={subtract}>Get premium.</button>
			<p>There's no other option...</p>
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
