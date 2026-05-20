<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import { page } from '$app/state';
	import { base } from '$app/paths';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		rel="stylesheet"
		href="https://fonts.googleapis.com/css2?family=Instrument+Serif&family=Inter:wght@300;400;500;600&display=swap"
	/>
</svelte:head>

<div class="app">
	<header class="header">
		<a class="brand" href="{base}/">
			<span class="brand-mark" aria-hidden="true">
				<svg viewBox="0 0 32 32" width="28" height="28">
					<path
						d="M16 3c-2 4-5 6-9 6 1 5 4 9 9 12 5-3 8-7 9-12-4 0-7-2-9-6Z"
						fill="none"
						stroke="currentColor"
						stroke-width="1.4"
						stroke-linejoin="round"
					/>
					<path
						d="M16 9v13"
						stroke="currentColor"
						stroke-width="1.4"
						stroke-linecap="round"
					/>
				</svg>
			</span>
			<span class="brand-text">
				<strong>Aromatica</strong>
				<em>натуральные эфирные масла</em>
			</span>
		</a>

		<nav class="nav">
			<a href="{base}/" class:active={page.url.pathname === `${base}/`}>Главная</a>
			<a href="{base}/gaultheria" class:active={page.url.pathname === `${base}/gaultheria`}>Гаультерия</a>
			<a href="{base}/lemongrass" class:active={page.url.pathname === `${base}/lemongrass`}>Лемонграсс</a>
		</nav>
	</header>

	<main class="main">
		{@render children()}
	</main>

	<footer class="footer">
		<div class="footer-ornament" aria-hidden="true">
			<svg viewBox="0 0 60 12" width="60" height="12">
				<path
					d="M0 6h22M38 6h22M30 1c2 0 4 2 4 5s-2 5-4 5-4-2-4-5 2-5 4-5Z"
					fill="none"
					stroke="currentColor"
					stroke-width="1"
				/>
			</svg>
		</div>
		<p>© {new Date().getFullYear()} Aromatica · Природа в каждой капле</p>
	</footer>
</div>

<style>
	:global(:root) {
		--bg: #f4efe6;
		--bg-deep: #ebe4d4;
		--card: #ffffff;
		--card-hover: #faf6ec;
		--card-soft: #efe6d3;
		--border: #d6cbb3;
		--ink: #1d1a15;
		--ink-soft: #5a534a;
		--ink-muted: #928876;
		--accent: #a47864;
		--accent-bright: #7a5642;
		--danger: #9c4e3e;

		--font-display: 'Instrument Serif', 'Times New Roman', Georgia, serif;
		--font-body:
			'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif;

		--radius: 12px;
		--radius-lg: 18px;
		--shadow: 0 12px 32px rgba(60, 50, 40, 0.07);
	}

	:global(*),
	:global(*::before),
	:global(*::after) {
		box-sizing: border-box;
	}

	:global(html),
	:global(body) {
		margin: 0;
		padding: 0;
		background: var(--bg-deep);
		color: var(--ink);
		font-family: var(--font-body);
		font-size: 16px;
		line-height: 1.6;
		-webkit-font-smoothing: antialiased;
	}

	:global(a) {
		color: var(--accent-bright);
		text-decoration: none;
		transition: color 0.2s ease;
	}

	:global(a:hover) {
		color: var(--ink);
	}

	:global(h1),
	:global(h2),
	:global(h3) {
		font-family: var(--font-display);
		font-weight: 600;
		letter-spacing: 0.01em;
		margin: 0;
	}

	.app {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		background:
			radial-gradient(1100px 500px at 85% -8%, rgba(164, 120, 100, 0.07), transparent 60%),
			radial-gradient(900px 500px at -8% 20%, rgba(156, 78, 62, 0.04), transparent 60%),
			linear-gradient(180deg, var(--bg) 0%, var(--bg-deep) 100%);
	}

	.header {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 1.25rem clamp(1.25rem, 4vw, 3rem);
		border-bottom: 1px solid var(--border);
	}

	.brand {
		display: flex;
		align-items: center;
		gap: 0.85rem;
		color: var(--accent-bright);
	}

	.brand-mark {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		width: 42px;
		height: 42px;
		border-radius: 50%;
		border: 1px solid var(--accent);
		color: var(--accent-bright);
	}

	.brand-text {
		display: flex;
		flex-direction: column;
		line-height: 1.15;
	}

	.brand-text strong {
		font-family: var(--font-body);
		font-size: 0.9rem;
		font-weight: 500;
		letter-spacing: 0.34em;
		text-transform: uppercase;
		color: var(--ink);
	}

	.brand-text em {
		font-style: normal;
		font-size: 0.72rem;
		color: var(--ink-muted);
		letter-spacing: 0.16em;
		text-transform: uppercase;
	}

	.nav {
		display: flex;
		gap: 1.75rem;
	}

	.nav a {
		font-size: 0.95rem;
		font-weight: 500;
		letter-spacing: 0.04em;
		color: var(--ink-soft);
		padding: 0.35rem 0;
		position: relative;
	}

	.nav a:hover {
		color: var(--accent-bright);
	}

	.nav a.active {
		color: var(--accent-bright);
	}

	.nav a.active::after {
		content: '';
		position: absolute;
		bottom: -4px;
		left: 0;
		right: 0;
		height: 1px;
		background: var(--accent);
	}

	.main {
		flex: 1;
		width: 100%;
	}

	.footer {
		padding: 2.5rem 1rem 2rem;
		text-align: center;
		color: var(--ink-muted);
		font-size: 0.85rem;
		border-top: 1px solid var(--border);
	}

	.footer-ornament {
		color: var(--accent);
		display: inline-flex;
		margin-bottom: 0.5rem;
		opacity: 0.7;
	}

	@media (max-width: 560px) {
		.header {
			flex-direction: column;
			align-items: flex-start;
			gap: 1rem;
		}

		.nav {
			gap: 1.25rem;
		}
	}
</style>
