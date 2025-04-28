<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<script>
	function copyToClipboard() {
		navigator.clipboard.writeText("PixelTown.apexmc.co").then(() => {
			alert("Server IP copied to clipboard!");
		});
	}
</script>

<div class="hero-container">
	<section class="hero full-width">
			<h1>Welcome to PixelTown!</h1>
			<p>Your ultimate Pixelmon adventure awaits. Join our vibrant community today!</p>
			<div>
				<a href="/Join" class="cta-button">Join The Server!</a>
				<a href="/Store" class="cta-button secondary">Visit The Store</a>
			</div>
		<img src="/Chansey.png" alt="Chansey" class="decorative-pokemon" id="chansey-splash" style="width: 15%;">
	</section>
</div>

<div class="container" style="margin: 0">
	<section class="main-content">
		<div class="main-content-container">
			<div class="main-content-left">
				<h2>Welcome to PixelTown!</h2>
				<p>This is the official website for PixelTown, your gateway to an exciting Pixelmon adventure!</p>
				<p>Here, you can:</p>
				<ul>
					<li>Cast your votes using the <strong><a href="/Vote" class="main-links">Votes</a></strong> tab.</li>
					<li>Explore our <strong><a href="/Store" class="main-links">Store</a></strong> for unique and affordable items.</li>
					<li>Join the server by heading over to the <strong><a href="/Join" class="main-links">Join</a></strong> section.</li>
				</ul>
				<img src="/Togekiss.png" alt="Togekiss" style="width: 70%; display: block; margin: 0 auto;">
				<p style="font-size: 200%; text-align: center;">
					Come join us at 
					<a href="#" class="ip-link" on:click|preventDefault={copyToClipboard}>our server IP</a> 
					and be part of the fun!
				</p>
			</div>
		</div>
	</section>

	<div class="shop-section">
		<h3>Best Deal</h3>
		<div class="divider"></div>
		<div class="store-deal">
			<img src="/event.png" alt="Product Logo" class="product-logo">
			<div class="product-details">
				<p class="product-name">Product Name</p>
				<p class="product-price">$9.99</p>
			</div>
		</div>
		<div class="product-buttons">
			<a href="#" class="cta-button">Buy Now</a>
			<a href="#" class="cta-button secondary">See More</a>
		</div>
	</div>
</div>

<section class="recent-event">
	<div class="event-container">
		<img src="/event.png" alt="PixelTown Event" class="event-image" />
		<div class="event-details">
			<h2>PixelTown Has Officially Launched!</h2>
			<p>PixelTown is now live! Explore a unique Minecraft experience featuring survival gameplay, a towny system for building and managing towns, an economy system for trading and shops, custom plugins to enhance your adventure, and regular player events. Join a friendly and active community with custom Pokémon, expanded spawns, and exciting giveaways. Start your journey today and see what PixelTown has to offer!</p>
		</div>
	</div>
</section>