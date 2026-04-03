<script>
	//@ts-nocheck
	let input = $state('');
	let result = $state('');
	let needAd = $state(false);
	function add(num) {
		input += num;
	}

	function calculate() {
		needAd = true;
		result = input;
	}
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" />
<link
	href="https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200..1000;1,200..1000&display=swap"
	rel="stylesheet"
/>

{#if needAd}
	<ins
		class="adsbygoogle"
		style="display:inline-block;width:728px;height:90px"
		data-ad-client="ca-pub-1234567890123456"
		data-ad-slot="1234567890"
	></ins>
{:else}
	<div class="centerdiv">
		<h1>Ragebait Calculator</h1>

		<div class="divider"></div>
		<div class="calculator">
			<div class="screen">
				<h1>Input: {input}</h1>
				<h1>Result: {result}</h1>
			</div>

			<row>
				<button
					onclick={() => {
						add(1);
					}}>1</button
				>
				<button
					onclick={() => {
						add(2);
					}}>2</button
				>
				<button
					onclick={() => {
						add(3);
					}}>3</button
				>
			</row>
			<row>
				<button
					onclick={() => {
						add(4);
					}}>4</button
				>
				<button
					onclick={() => {
						add(5);
					}}>5</button
				>
				<button
					onclick={() => {
						add(6);
					}}>6</button
				>
			</row>
			<row>
				<button
					onclick={() => {
						add(7);
					}}>7</button
				>
				<button
					onclick={() => {
						add(8);
					}}>8</button
				>
				<button
					onclick={() => {
						add(9);
					}}>9</button
				>
			</row>
			<row>
				<button
					onclick={() => {
						add('*');
					}}>*</button
				>
				<button
					onclick={() => {
						add('+');
					}}>+</button
				>
				<button onclick={calculate}>=</button>
			</row>
		</div>
	</div>
{/if}
