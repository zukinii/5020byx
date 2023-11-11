<script>
	const metaData = {
		title: '5020Byx - Fahrradwerkstatt in Salzburg',
		description: 'Fahrradwerkstatt in Salzburg'
	}

	const contactData = {
		phone: {
			label: 'Telefon',
			cta: 'Jetzt Anrufen',
			value: '+43 123 456 789',
			href: 'tel:+43123456789'
		},
		email: {
			label: 'E-Mail',
			cta: 'Jetzt E-Mail schreiben',
			value: '',
			href: '#contact'
		},
		address: {
			label: 'Adresse',
			cta: 'Route anzeigen',
			value: '',
			href: 'https://www.google.com/maps/dir//5020Byx/data=!4m8!4m7!1m0!1m5!1m1!1s0x4776918dbedf7b49:0x3957a6a60ebcc5dc!2m2!1d13.055804199999999!2d47.8077027'
		}
	}
</script>

<svelte:head>
	<title>{metaData.title}</title>
	<meta name="description" content={metaData.description} />
	<meta property="og:type" content="website" />
	<meta name="og:title" content={metaData.title} />
	<meta name="og:description" content={metaData.description} />
	<meta property="og:image" content="/img/og-image.jpg" />
	<meta name="theme-color" content="#000000" />
</svelte:head>

<header class="nav">
	<div class="border-left" />
	<div class="border-right" />
	<a href="/" class="logo">
		<img src="" alt="5020byx" />
	</a>
	<nav>
		<a href={contactData.phone.href}>{contactData.phone.cta}</a>
		<a href={contactData.email.href}>{contactData.email.cta}</a>
		<a href={contactData.address.href}>{contactData.address.cta}</a>
	</nav>
</header>
<main>
	<header class="hero">
		<div class="hero-text">
			<h1>5020BYX</h1>
			<p>Fahrradwerkstatt in Salzburg<br />Öffnet am Dienstag um 10:00</p>
			<a href="cta">CTA</a>
		</div>
		<picture>
			<!--source srcset="x" media="(min-width: 320px)" /-->
			<img src="/img/bike.jpg" alt="a stylish city bike leaned against a garden wall" />
		</picture>
	</header>
	<section class="about-us">
		<p>
			Besuche uns bei 5020BYX in Schallmoos, Salzburg, und tauche ein in die Welt der maßgefertigten
			Fahrräder. Wir sind stolz darauf, Teil der Fahrradgemeinschaft zu sein, und freuen uns darauf,
			dich auf deinem nächsten zweirädrigen Abenteuer zu begleiten.
		</p>
	</section>
	<section class="contact">
		<iframe
			src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2679.6456582375445!2d13.055811400000001!3d47.8077042!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x4776918dbedf7b49%3A0x3957a6a60ebcc5dc!2s5020Byx!5e0!3m2!1sen!2sat!4v1699728602790!5m2!1sen!2sat"
			width="600"
			height="450"
			style="border:0;"
			allowfullscreen=""
			loading="lazy"
			referrerpolicy="no-referrer-when-downgrade"
			title="Google Map of 5020Byx"
		/>
	</section>
</main>
<footer>x</footer>

<style>
	.nav {
		--bg-color: var(--green-9);
		--border-width: var(--size-2);

		padding-inline: var(--border-width);
		position: sticky;
		top: 0;
		left: 0;
		right: 0;
		min-height: 4rem;
		background-color: var(--bg-color);
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.nav .border-left,
	.nav .border-right {
		position: fixed;
		top: 0;
		bottom: 0;
		width: var(--border-width);
		background-color: var(--bg-color);
	}

	.nav .border-left {
		left: 0;
	}

	.nav .border-right {
		right: 0;
	}

	.nav nav {
		display: flex;
		align-items: center;
		gap: var(--size-2);
	}

	main {
		min-height: 100vh;
		background-color: #f5f5f5;
	}

	.hero {
		display: grid;
		grid-template-columns: minmax(0, 1fr);
		justify-items: center;
	}

	.about-us {
		min-height: 50vh;
		display: grid;
		place-items: center;
		text-align: center;
		scroll-timeline-name: --squareTimeline;
	}

	@keyframes scale-up {
		to {
			scale: 1.5;
		}
	}

	.about-us p {
		font-size: var(--size-4);
		margin-inline: auto;
		max-width: 70ch;

		animation-name: scale-up;
		animation-duration: 1ms; /* Firefox requires this to apply the animation */
		animation-direction: alternate;
		animation-timeline: --squareTimeline;
	}

	@supports (animation-timeline: view()) {
		.about-us p {
		}
	}

	footer {
		--bg-color: var(--green-9);

		min-height: 4rem;
		background-color: var(--bg-color);
	}
</style>
