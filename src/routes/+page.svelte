<script lang="ts">
	import { base } from '$app/paths';
	import Durga from '$lib/emblems/Durga.svelte';
	import Shiva from '$lib/emblems/Shiva.svelte';

	const oils = [
		{
			slug: 'gaultheria',
			name: 'Гаультерия',
			latin: 'Gaultheria procumbens',
			note: 'Освежающий, прохладно-камфорный, с лёгкой древесной сладостью',
			tags: ['обезболивающее', 'противовоспалительное', 'заземление'],
			available: true,
			deity: 'Дурга',
			emblem: Durga,
			color: '#9C2D3F'
		},
		{
			slug: 'lemongrass',
			name: 'Лемонграсс',
			latin: 'Cymbopogon flexuosus',
			note: 'Свежий цитрусово-травяной, очищающий и тонизирующий',
			tags: ['антибактериальное', 'очищение', 'тонус'],
			available: true,
			deity: 'Шива',
			emblem: Shiva,
			color: '#0E8A56'
		},
		{
			slug: '',
			name: 'Лаванда',
			latin: 'Lavandula angustifolia',
			note: 'Тёплый цветочный аромат с травянистыми нотами',
			tags: ['успокаивающее', 'сон'],
			available: false,
			deity: 'Сарасвати',
			emblem: null,
			color: '#8E6AC8'
		},
		{
			slug: '',
			name: 'Эвкалипт',
			latin: 'Eucalyptus globulus',
			note: 'Свежий, ментоловый, очищающий',
			tags: ['дыхание', 'тонус'],
			available: false,
			deity: 'Хануман',
			emblem: null,
			color: '#0FB5AE'
		}
	];
</script>

<section class="hero">
	<div class="hero-inner">
		<span class="eyebrow">эфирные масла · ручная коллекция</span>
		<h1>Аромат природы<br /><em>в каждой капле</em></h1>
		<p class="lede">
			Чистые эфирные масла прямой паровой дистилляции. Каждое масло — это история растения,
			его свойств, традиций применения и энергетики.
		</p>
		<div class="hero-cta">
			<a href="{base}/gaultheria" class="btn-primary">Узнать о гаультерии</a>
			<a href="#collection" class="btn-ghost">Коллекция</a>
		</div>
	</div>
	<div class="hero-ornament" aria-hidden="true">
		<svg viewBox="0 0 200 200" width="220" height="220">
			<g fill="none" stroke="currentColor" stroke-width="0.8" opacity="0.5">
				<circle cx="100" cy="100" r="80" />
				<circle cx="100" cy="100" r="60" />
				<circle cx="100" cy="100" r="40" />
				<path d="M100 20v160M20 100h160M40 40l120 120M160 40 40 160" />
				<path
					d="M100 40c20 25 20 95 0 120-20-25-20-95 0-120ZM40 100c25-20 95-20 120 0-25 20-95 20-120 0Z"
				/>
			</g>
		</svg>
	</div>
</section>

<section class="collection" id="collection">
	<header class="section-head">
		<span class="ornament" aria-hidden="true">◈</span>
		<h2>Наша коллекция</h2>
		<p>Каждое масло — отдельная страница с подробным описанием, способами применения и эзотерикой</p>
	</header>

	<div class="grid">
		{#each oils as oil (oil.name)}
			{#if oil.available && oil.emblem}
				{@const Emblem = oil.emblem}
				<a class="card" href="{base}/{oil.slug}">
					<div class="emblem" style="color: {oil.color}; --emblem-color: {oil.color};">
						<Emblem />
					</div>
					<p class="deity">{oil.deity}</p>
					<h3>{oil.name}</h3>
					<p class="latin">{oil.latin}</p>
					<p class="note">{oil.note}</p>
					<div class="tags">
						{#each oil.tags as tag (tag)}
							<span class="tag">{tag}</span>
						{/each}
					</div>
					<span class="card-arrow">Подробнее →</span>
				</a>
			{:else}
				<div class="card card-disabled">
					<div class="emblem emblem-placeholder" aria-hidden="true">
						<svg viewBox="0 0 100 100" width="100%" height="100%">
							<circle
								cx="50"
								cy="50"
								r="42"
								fill="none"
								stroke="currentColor"
								stroke-width="0.9"
								opacity="0.4"
							/>
							<circle
								cx="50"
								cy="50"
								r="46"
								fill="none"
								stroke="currentColor"
								stroke-width="0.6"
								opacity="0.3"
							/>
							<text
								x="50"
								y="58"
								text-anchor="middle"
								font-family="Cormorant Garamond, serif"
								font-style="italic"
								font-size="14"
								fill="currentColor"
								opacity="0.5">скоро</text
							>
						</svg>
					</div>
					<p class="deity muted">{oil.deity}</p>
					<h3>{oil.name}</h3>
					<p class="latin">{oil.latin}</p>
					<p class="note">{oil.note}</p>
					<div class="tags">
						{#each oil.tags as tag (tag)}
							<span class="tag">{tag}</span>
						{/each}
					</div>
					<span class="card-arrow muted">Скоро</span>
				</div>
			{/if}
		{/each}
	</div>
</section>

<style>
	.hero {
		position: relative;
		max-width: 1180px;
		margin: 0 auto;
		padding: 5rem clamp(1.25rem, 4vw, 3rem) 4rem;
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 3rem;
		overflow: hidden;
	}

	.hero-inner {
		max-width: 620px;
	}

	.eyebrow {
		display: inline-block;
		font-size: 0.75rem;
		letter-spacing: 0.28em;
		text-transform: uppercase;
		color: var(--accent);
		margin-bottom: 1.5rem;
	}

	.hero h1 {
		font-size: clamp(2.5rem, 5vw, 4rem);
		line-height: 1.05;
		color: var(--ink);
		margin-bottom: 1.5rem;
	}

	.hero h1 em {
		font-style: italic;
		font-weight: 400;
		color: var(--accent-bright);
	}

	.lede {
		font-size: 1.1rem;
		color: var(--ink-soft);
		max-width: 520px;
		margin: 0 0 2rem;
	}

	.hero-cta {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
	}

	.btn-primary,
	.btn-ghost {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		padding: 0.85rem 1.6rem;
		border-radius: 999px;
		font-weight: 500;
		font-size: 0.95rem;
		letter-spacing: 0.04em;
		transition: all 0.25s ease;
	}

	.btn-primary {
		background: var(--accent-bright);
		color: #fff;
		border: 1px solid var(--accent-bright);
	}

	.btn-primary:hover {
		background: #4a5c39;
		border-color: #4a5c39;
		color: #fff;
		transform: translateY(-1px);
	}

	.btn-ghost {
		border: 1px solid rgba(122, 138, 106, 0.35);
		color: var(--ink);
	}

	.btn-ghost:hover {
		border-color: var(--accent);
		color: var(--accent-bright);
	}

	.hero-ornament {
		color: var(--accent);
		opacity: 0.35;
		flex-shrink: 0;
	}

	@media (max-width: 880px) {
		.hero-ornament {
			display: none;
		}
	}

	.collection {
		max-width: 1180px;
		margin: 0 auto;
		padding: 3rem clamp(1.25rem, 4vw, 3rem) 5rem;
	}

	.section-head {
		text-align: center;
		margin-bottom: 3rem;
	}

	.section-head .ornament {
		display: block;
		color: var(--accent);
		font-size: 1.5rem;
		margin-bottom: 0.5rem;
		opacity: 0.7;
	}

	.section-head h2 {
		font-size: clamp(1.75rem, 3.5vw, 2.4rem);
		color: var(--ink);
		margin-bottom: 0.5rem;
	}

	.section-head p {
		color: var(--ink-muted);
		max-width: 560px;
		margin: 0 auto;
	}

	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		gap: 1.5rem;
	}

	.card {
		background: var(--card);
		border: 1px solid rgba(122, 138, 106, 0.18);
		border-radius: var(--radius-lg);
		padding: 2rem 1.75rem;
		color: var(--ink);
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		transition: all 0.3s ease;
		position: relative;
		overflow: hidden;
	}

	.card:not(.card-disabled):hover {
		background: var(--card-hover);
		border-color: rgba(122, 138, 106, 0.4);
		transform: translateY(-3px);
		box-shadow: var(--shadow);
	}

	.card-disabled {
		opacity: 0.55;
		cursor: not-allowed;
	}

	.emblem {
		width: 84px;
		height: 84px;
		margin: 0 auto 1rem;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 50%;
		background: var(--card-soft);
		padding: 14px;
		transition: transform 0.4s ease, box-shadow 0.4s ease;
	}

	.card:not(.card-disabled):hover .emblem {
		transform: scale(1.05);
		box-shadow: 0 6px 18px rgba(60, 70, 50, 0.08);
	}

	.emblem :global(svg) {
		width: 100%;
		height: 100%;
	}

	.emblem-placeholder {
		color: var(--ink-muted);
	}

	.deity {
		text-align: center;
		font-family: var(--font-display);
		font-style: italic;
		font-size: 0.8rem;
		letter-spacing: 0.24em;
		text-transform: uppercase;
		color: var(--accent);
		margin: 0 0 0.25rem;
	}

	.deity.muted {
		color: var(--ink-muted);
	}

	.card h3 {
		font-size: 1.5rem;
		color: var(--ink);
		text-align: center;
	}

	.card .latin,
	.card .note {
		text-align: center;
	}

	.card .latin {
		font-style: italic;
		color: var(--ink-muted);
		font-size: 0.9rem;
		margin: 0;
	}

	.card .note {
		color: var(--ink-soft);
		font-size: 0.95rem;
		margin: 0.5rem 0 0.75rem;
		line-height: 1.5;
	}

	.tags {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		gap: 0.4rem;
		margin-bottom: 1rem;
	}

	.tag {
		font-size: 0.72rem;
		padding: 0.25rem 0.7rem;
		border-radius: 999px;
		background: rgba(122, 138, 106, 0.12);
		color: var(--ink-soft);
		letter-spacing: 0.04em;
	}

	.card-arrow {
		margin-top: auto;
		text-align: center;
		color: var(--accent-bright);
		font-size: 0.9rem;
		font-weight: 500;
		letter-spacing: 0.04em;
	}

	.card-arrow.muted {
		color: var(--ink-muted);
		font-style: italic;
	}
</style>
