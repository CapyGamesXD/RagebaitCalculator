<script>
	//@ts-nocheck

	let input = $state('');
	let result = $state('');
	let needAd = $state(false);
	let timeLeft = $state();
	let guessing = $state(false);
	let randomElement;
	function add(num) {
		input += num;
	}

	function calculate() {
		needAd = true;

		timeLeft = 10;
		let images = ['/CapyDesigns.jpg', '/image.png', '/artwork.webp'];
		randomElement = images[Math.floor(Math.random() * images.length)];

		const timer = setInterval(() => {
			if (timeLeft > 0) {
				timeLeft -= 1;
			} else {
				clearInterval(timer);
				needAd = false;
				result = input;
			}
		}, 1000);
	}
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" />
<link
	href="https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200..1000;1,200..1000&display=swap"
	rel="stylesheet"
/>

{#if needAd}
	<div class="centerdiv">
		<h1>Watch and ad to get your 'technically correct' answer!</h1>
		<img src={randomElement} alt="Ad" />

		<h1>Time left on ad: {timeLeft}</h1>
	</div>
{:else}
	<div class="centerdiv">
		<h1>Ragebait Calculator</h1>
		<p>Completely useless</p>

		<div class="divider"></div>
		<div class="calculator">
			<div class="screen">
				<h1>Input: {input}</h1>
				{#if result}
					<h1>Answer = {result}; You're welcome. :D</h1>
				{:else}
					<h1>Click the '=' to get your answer</h1>
				{/if}
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
						add('x');
					}}>x</button
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
