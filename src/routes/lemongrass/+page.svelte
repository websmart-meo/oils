<script lang="ts">
	import { base } from '$app/paths';
	import Shiva from '$lib/emblems/Shiva.svelte';

	type Item = { title: string; text: string };

	const physical: Item[] = [
		{
			title: 'Антибактериальное и противогрибковое действие',
			text: 'Эффективно борется с бактериями и грибками, что делает его полезным для лечения кожных инфекций.'
		},
		{
			title: 'Противовоспалительное действие',
			text: 'Помогает уменьшить воспаление и облегчить боль.'
		},
		{
			title: 'Антиоксидантные свойства',
			text: 'Содержит антиоксиданты, которые помогают защитить клетки от повреждений, вызванных свободными радикалами.'
		},
		{
			title: 'Тонизирующее действие',
			text: 'Помогает повысить уровень энергии и улучшить настроение.'
		},
		{
			title: 'Улучшение пищеварения',
			text: 'Может помочь при проблемах с пищеварением, таких как вздутие живота и спазмы.'
		},
		{
			title: 'Репеллентные свойства',
			text: 'Лемонграссовое масло отпугивает насекомых, таких как комары.'
		},
		{
			title: 'Уход за кожей',
			text: 'Помогает уменьшить жирность кожи и сузить поры — полезно для ухода за жирной и проблемной кожей.'
		}
	];

	const energetic: Item[] = [
		{
			title: 'Повышение энергии',
			text: 'Помогает повысить уровень энергии и бодрости — отличное средство для борьбы с усталостью и апатией.'
		},
		{
			title: 'Стимуляция умственной активности',
			text: 'Способствует улучшению концентрации и ясности ума, полезно при умственной работе и учёбе.'
		},
		{
			title: 'Тонизирующее действие',
			text: 'Помогает тонизировать организм, улучшая общее состояние и повышая работоспособность.'
		}
	];

	const emotional: Item[] = [
		{
			title: 'Снятие стресса и тревоги',
			text: 'Обладает успокаивающим эффектом, помогая снизить уровень стресса и тревоги.'
		},
		{
			title: 'Улучшение настроения',
			text: 'Аромат способствует улучшению настроения и созданию позитивного эмоционального фона.'
		},
		{
			title: 'Снятие напряжения',
			text: 'Помогает расслабиться и снять эмоциональное напряжение, что полезно после напряжённого дня.'
		},
		{
			title: 'Балансировка эмоций',
			text: 'Помогает сбалансировать эмоции, создавая ощущение внутреннего покоя и гармонии.'
		}
	];

	const esoteric: Item[] = [
		{
			title: 'Энергетическая чистка пространства',
			text: 'Обладает сильными очищающими свойствами и эффективно устраняет застойную, негативную энергию. Используется для очищения дома, рабочего места и личного энергетического поля.'
		},
		{
			title: 'Удаление энергетических блоков',
			text: 'Помогает устранить блоки и препятствия, мешающие свободному течению жизненной энергии. Способствует обновлению и активизации энергетических потоков в теле.'
		},
		{
			title: 'Повышение вибраций',
			text: 'Аромат поднимает энергетический уровень, помогает выйти из состояния уныния и апатии.'
		},
		{
			title: 'Защита от негатива',
			text: 'Создаёт энергетический щит, который защищает от чужого негатива.'
		},
		{
			title: 'Активация личной силы',
			text: 'Помогает пробудить внутреннюю силу и уверенность в себе.'
		}
	];

	const usage: Item[] = [
		{
			title: 'Диффузор',
			text: 'Добавьте 3–5 капель масла в диффузор, чтобы наполнить помещение свежим и бодрящим ароматом.'
		},
		{
			title: 'Аромалампа',
			text: 'Добавьте несколько капель масла в аромалампу с водой, чтобы создать расслабляющую атмосферу.'
		},
		{
			title: 'Массажное масло',
			text: 'Смешайте 2–3 капли масла лемонграсса с 1 столовой ложкой базового масла (кокосового или миндального) и используйте для массажа. Снимает мышечное напряжение и боль.'
		},
		{
			title: 'Точечный массаж',
			text: 'Нанесите разбавленное масло на конкретные точки на теле для облегчения боли и расслабления.'
		},
		{
			title: 'Тёплый компресс',
			text: 'Добавьте 2–3 капли масла в тёплую воду, смочите ткань и приложите к больному месту для снятия воспаления и боли.'
		},
		{
			title: 'Холодный компресс',
			text: 'Используйте холодную воду вместо тёплой для уменьшения отёков и воспалений.'
		},
		{
			title: 'Ароматическая ванна',
			text: 'Добавьте 5–10 капель масла в ванну с тёплой водой. Помогает расслабиться и снять мышечное напряжение.'
		},
		{
			title: 'Ножные ванны',
			text: 'Добавьте 2–3 капли масла в таз с тёплой водой и погрузите ноги на 10–15 минут для снятия усталости и боли.'
		},
		{
			title: 'Лечение акне',
			text: 'Смешайте 1 каплю масла лемонграсса с 1 чайной ложкой базового масла и нанесите на проблемные участки кожи.'
		},
		{
			title: 'Антисептическое средство',
			text: 'Используйте разбавленное масло для обработки мелких порезов и ран.'
		},
		{
			title: 'Паровые ингаляции',
			text: 'Добавьте 2–3 капли масла в миску с горячей водой, наклонитесь над ней, накрыв голову полотенцем, и вдыхайте пар для облегчения симптомов простуды и улучшения дыхания.'
		},
		{
			title: 'Освежитель воздуха',
			text: 'Добавьте несколько капель масла в воду и распылите в помещении для свежего аромата.'
		},
		{
			title: 'Чистящие средства',
			text: 'Масло можно использовать в составе натуральных чистящих средств для дезинфекции поверхностей.'
		}
	];

	const warnings: Item[] = [
		{
			title: 'Проверьте на аллергию',
			text: 'Проведите тест на небольшом участке кожи перед первым применением.'
		},
		{
			title: 'Разбавляйте масло',
			text: 'Используйте базовое масло для разбавления. Избегайте контакта с глазами. Не наносите на повреждённую кожу.'
		},
		{
			title: 'Беременность и кормление грудью',
			text: 'Проконсультируйтесь с врачом. Не использовать длительно без перерывов.'
		},
		{ title: 'Не использовать внутрь!', text: 'Масло предназначено только для наружного применения.' },
		{ title: 'Возрастные ограничения', text: 'Избегайте использования для детей младше 12 лет.' }
	];

	const info = [
		{ label: 'Латинское название', value: 'Cymbopogon flexuosus' },
		{ label: 'Состав', value: '100% чистое эфирное масло лемонграсса' },
		{ label: 'Объём', value: '10 мл' },
		{ label: 'Способ получения', value: 'Паровая дистилляция' },
		{ label: 'Срок годности', value: '5 лет (13.06.2024 — 12.06.2029)' },
		{ label: 'Страна происхождения', value: 'Индия' }
	];
</script>

<svelte:head>
	<title>Эфирное масло лемонграсса — Aromatica</title>
	<meta
		name="description"
		content="Эфирное масло лемонграсса (Cymbopogon flexuosus) — свежий цитрусовый аромат, антибактериальное действие, очищение пространства и эзотерика."
	/>
</svelte:head>

<article class="page lemon">
	<header class="hero">
		<a class="back-link" href="{base}/">← Назад к коллекции</a>

		<div class="hero-grid">
			<div class="hero-text">
				<div class="deity-seal" style="color: #0E8A56;">
					<Shiva />
					<span class="deity-name">Шива</span>
				</div>
				<span class="eyebrow">эфирное масло · паровая дистилляция</span>
				<h1>Лемонграсс</h1>
				<p class="latin">Cymbopogon flexuosus</p>
				<p class="lede">
					Свежий цитрусово-травяной аромат, очищающий пространство и поднимающий вибрации.
					Антибактериальный, тонизирующий, отпугивает насекомых и пробуждает личную силу.
				</p>
				<div class="badges">
					<span class="badge">Антибактериальное</span>
					<span class="badge">Тонизирующее</span>
					<span class="badge">Очищение</span>
					<span class="badge">10 мл</span>
				</div>
			</div>

			<div class="hero-visual" aria-hidden="true">
				<div class="bottle">
					<div class="bottle-cap"></div>
					<div class="bottle-neck"></div>
					<div class="bottle-body">
						<div class="bottle-label">
							<span>Lemongrass</span>
							<em>Cymbopogon flexuosus</em>
						</div>
						<div class="bottle-shine"></div>
					</div>
				</div>
				<svg class="mandala" viewBox="0 0 300 300" width="300" height="300">
					<g
						fill="none"
						stroke="currentColor"
						stroke-width="0.6"
						opacity="0.4"
						transform="translate(150 150)"
					>
						<circle r="140" />
						<circle r="115" />
						<circle r="90" />
						<circle r="65" />
						{#each Array(16) as _, i (i)}
							<g transform="rotate({i * 22.5})">
								<path
									d="M0 -140c10 22 10 56 0 78-10-22-10-56 0-78ZM0 -115c8 15 8 40 0 55-8-15-8-40 0-55Z"
								/>
							</g>
						{/each}
					</g>
				</svg>
				<div class="citrus-glow"></div>
			</div>
		</div>
	</header>

	<section class="section">
		<div class="section-head">
			<span class="section-num">01</span>
			<h2>Свойства</h2>
			<p>Природное действие на тело, кожу и пространство вокруг</p>
		</div>
		<div class="cards">
			{#each physical as item (item.title)}
				<div class="prop-card">
					<div class="prop-icon" aria-hidden="true">
						<svg viewBox="0 0 24 24" width="22" height="22">
							<path
								d="M3 12c4-6 14-6 18 0-4 6-14 6-18 0Z"
								fill="none"
								stroke="currentColor"
								stroke-width="1.4"
								stroke-linejoin="round"
							/>
							<path
								d="M12 6v12"
								stroke="currentColor"
								stroke-width="1.2"
								stroke-linecap="round"
								opacity="0.6"
							/>
						</svg>
					</div>
					<h3>{item.title}</h3>
					<p>{item.text}</p>
				</div>
			{/each}
		</div>
	</section>

	<section class="section section-alt">
		<div class="section-head">
			<span class="section-num">02</span>
			<h2>Энергетические свойства</h2>
		</div>
		<div class="cards cards-compact">
			{#each energetic as item (item.title)}
				<div class="prop-card prop-card-soft">
					<h3>{item.title}</h3>
					<p>{item.text}</p>
				</div>
			{/each}
		</div>
	</section>

	<section class="section">
		<div class="section-head">
			<span class="section-num">03</span>
			<h2>Эмоциональные свойства</h2>
		</div>
		<div class="cards cards-compact">
			{#each emotional as item (item.title)}
				<div class="prop-card prop-card-soft">
					<h3>{item.title}</h3>
					<p>{item.text}</p>
				</div>
			{/each}
		</div>
	</section>

	<section class="section section-mystic">
		<div class="section-head">
			<span class="section-num">04</span>
			<h2>Эзотерические свойства</h2>
			<p>Очищение энергетики, защита и активация личной силы</p>
		</div>
		<div class="cards">
			{#each esoteric as item (item.title)}
				<div class="prop-card prop-card-mystic">
					<div class="prop-icon" aria-hidden="true">◈</div>
					<h3>{item.title}</h3>
					<p>{item.text}</p>
				</div>
			{/each}
		</div>
	</section>

	<section class="section">
		<div class="section-head">
			<span class="section-num">05</span>
			<h2>Способы применения</h2>
			<p>Тринадцать способов раскрыть масло — от диффузора до точечного нанесения</p>
		</div>
		<div class="usage-list">
			{#each usage as item, i (item.title)}
				<div class="usage-item">
					<span class="usage-num">{String(i + 1).padStart(2, '0')}</span>
					<div class="usage-body">
						<h3>{item.title}</h3>
						<p>{item.text}</p>
					</div>
				</div>
			{/each}
		</div>
	</section>

	<section class="section warnings-section">
		<div class="section-head">
			<span class="section-num">06</span>
			<h2>Предупреждения</h2>
			<p>Эфирные масла концентрированы — соблюдайте безопасность</p>
		</div>
		<div class="cards">
			{#each warnings as item (item.title)}
				<div class="warning-card">
					<div class="warning-icon" aria-hidden="true">
						<svg viewBox="0 0 24 24" width="20" height="20">
							<path
								d="M12 3 1.5 21h21L12 3Zm0 6v6m0 3v.5"
								fill="none"
								stroke="currentColor"
								stroke-width="1.6"
								stroke-linecap="round"
								stroke-linejoin="round"
							/>
						</svg>
					</div>
					<div>
						<h3>{item.title}</h3>
						<p>{item.text}</p>
					</div>
				</div>
			{/each}
		</div>
	</section>

	<section class="section">
		<div class="section-head">
			<span class="section-num">07</span>
			<h2>Хранение и общая информация</h2>
		</div>

		<div class="info-grid">
			<div class="storage-card">
				<div class="storage-icon" aria-hidden="true">
					<svg viewBox="0 0 24 24" width="28" height="28">
						<path
							d="M8 2h8v3l-2 2v11a3 3 0 0 1-4 0V7L8 5V2Z"
							fill="none"
							stroke="currentColor"
							stroke-width="1.4"
							stroke-linejoin="round"
						/>
					</svg>
				</div>
				<h3>Условия хранения</h3>
				<p>
					Хранить в плотно закрытом флаконе, в тёмном прохладном месте, вдали от детей и
					открытого огня.
				</p>
			</div>

			<dl class="info-card">
				{#each info as item (item.label)}
					<div class="info-row">
						<dt>{item.label}</dt>
						<dd>{item.value}</dd>
					</div>
				{/each}
			</dl>
		</div>

		<div class="manufacturer">
			<h3>Производитель</h3>
			<p>
				<strong>M/s. P. Sridhar & Co.</strong><br />
				153-A, Ganesh Hall, Walsham Road<br />
				<a href="https://www.ganesheucalyptus.in" target="_blank" rel="noopener noreferrer"
					>ganesheucalyptus.in</a
				> · +91 98431 75690
			</p>
		</div>
	</section>
</article>

<style>
	.page {
		max-width: 1180px;
		margin: 0 auto;
		padding: 0 clamp(1.25rem, 4vw, 3rem);
	}

	.lemon {
		--accent-hue: #b08a3a;
	}

	.hero {
		padding: 2.5rem 0 4rem;
		border-bottom: 1px solid rgba(122, 138, 106, 0.15);
	}

	.back-link {
		display: inline-block;
		font-size: 0.88rem;
		color: var(--ink-muted);
		letter-spacing: 0.04em;
		margin-bottom: 2.5rem;
	}

	.back-link:hover {
		color: var(--accent-bright);
	}

	.hero-grid {
		display: grid;
		grid-template-columns: 1.2fr 1fr;
		gap: 4rem;
		align-items: center;
	}

	@media (max-width: 900px) {
		.hero-grid {
			grid-template-columns: 1fr;
			gap: 2.5rem;
		}
	}

	.eyebrow {
		display: inline-block;
		font-size: 0.72rem;
		letter-spacing: 0.32em;
		text-transform: uppercase;
		color: var(--accent);
		margin-bottom: 1.25rem;
	}

	.deity-seal {
		display: flex;
		align-items: center;
		gap: 0.85rem;
		margin-bottom: 1.5rem;
	}

	.deity-seal :global(svg) {
		width: 56px;
		height: 56px;
		flex-shrink: 0;
	}

	.deity-name {
		font-family: var(--font-display);
		font-style: italic;
		font-size: 1rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
		color: currentColor;
	}

	.hero h1 {
		font-size: clamp(3rem, 7vw, 5.5rem);
		font-style: italic;
		font-weight: 500;
		color: var(--ink);
		line-height: 1;
		margin-bottom: 0.5rem;
	}

	.hero .latin {
		font-family: var(--font-display);
		font-style: italic;
		font-size: 1.3rem;
		color: var(--accent-bright);
		margin: 0 0 1.5rem;
	}

	.lede {
		font-size: 1.1rem;
		color: var(--ink-soft);
		line-height: 1.7;
		margin: 0 0 2rem;
		max-width: 540px;
	}

	.badges {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem;
	}

	.badge {
		font-size: 0.78rem;
		padding: 0.4rem 0.9rem;
		border-radius: 999px;
		background: rgba(170, 145, 60, 0.12);
		border: 1px solid rgba(170, 145, 60, 0.3);
		color: var(--ink-soft);
		letter-spacing: 0.04em;
	}

	.hero-visual {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
		min-height: 360px;
	}

	.citrus-glow {
		position: absolute;
		inset: -10%;
		background: radial-gradient(
			ellipse at center,
			rgba(170, 145, 60, 0.15),
			transparent 60%
		);
		z-index: 0;
		pointer-events: none;
	}

	.mandala {
		position: absolute;
		color: var(--accent-hue);
		z-index: 0;
		animation: rotate-r 75s linear infinite;
	}

	@keyframes rotate-r {
		to {
			transform: rotate(-360deg);
		}
	}

	.bottle {
		position: relative;
		z-index: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		filter: drop-shadow(0 20px 40px rgba(0, 0, 0, 0.4));
	}

	.bottle-cap {
		width: 50px;
		height: 26px;
		background: linear-gradient(180deg, #7a6f44 0%, #463f25 100%);
		border-radius: 6px 6px 3px 3px;
		border-top: 1px solid #9c8e58;
	}

	.bottle-neck {
		width: 30px;
		height: 18px;
		background: linear-gradient(180deg, #2d3a26 0%, #1c2618 100%);
		border-left: 1px solid rgba(255, 255, 255, 0.05);
		border-right: 1px solid rgba(0, 0, 0, 0.3);
	}

	.bottle-body {
		position: relative;
		width: 130px;
		height: 200px;
		background: linear-gradient(135deg, #303d29 0%, #1d251a 60%, #2c3825 100%);
		border-radius: 12px 12px 18px 18px;
		border: 1px solid rgba(170, 145, 60, 0.08);
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
	}

	.bottle-label {
		text-align: center;
		color: var(--accent-bright);
		font-family: var(--font-display);
		padding: 0.8rem;
		border: 1px solid rgba(170, 145, 60, 0.55);
		border-radius: 6px;
		background: rgba(0, 0, 0, 0.22);
	}

	.bottle-label span {
		display: block;
		font-size: 1.05rem;
		font-weight: 600;
		letter-spacing: 0.08em;
	}

	.bottle-label em {
		font-size: 0.68rem;
		font-style: italic;
		color: var(--ink-muted);
		letter-spacing: 0.04em;
	}

	.bottle-shine {
		position: absolute;
		top: 8%;
		left: 12%;
		width: 12px;
		height: 60%;
		background: linear-gradient(180deg, rgba(255, 255, 255, 0.18), transparent);
		border-radius: 6px;
		pointer-events: none;
	}

	.section {
		padding: 4rem 0;
		border-bottom: 1px solid rgba(122, 138, 106, 0.1);
	}

	.section:last-of-type {
		border-bottom: none;
	}

	.section-alt {
		background: linear-gradient(180deg, transparent, rgba(170, 145, 60, 0.04), transparent);
	}

	.section-mystic {
		position: relative;
	}

	.section-mystic::before {
		content: '';
		position: absolute;
		inset: 0;
		background: radial-gradient(
			ellipse at center,
			rgba(170, 145, 60, 0.06),
			transparent 70%
		);
		pointer-events: none;
	}

	.section-head {
		margin-bottom: 2.5rem;
		max-width: 720px;
	}

	.section-num {
		display: inline-block;
		font-family: var(--font-display);
		font-size: 0.85rem;
		color: var(--accent);
		letter-spacing: 0.2em;
		margin-bottom: 0.5rem;
	}

	.section-head h2 {
		font-size: clamp(1.8rem, 3.5vw, 2.4rem);
		color: var(--ink);
		font-style: italic;
		font-weight: 500;
		margin-bottom: 0.5rem;
	}

	.section-head p {
		color: var(--ink-muted);
		margin: 0;
	}

	.cards {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
		gap: 1.25rem;
	}

	.cards-compact {
		grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
	}

	.prop-card {
		background: var(--card);
		border: 1px solid rgba(122, 138, 106, 0.18);
		border-radius: var(--radius);
		padding: 1.5rem;
		transition: all 0.3s ease;
	}

	.prop-card:hover {
		border-color: rgba(170, 145, 60, 0.45);
		transform: translateY(-2px);
		box-shadow: var(--shadow);
	}

	.prop-icon {
		color: var(--accent-hue);
		margin-bottom: 0.75rem;
		font-size: 1.1rem;
	}

	.prop-card h3 {
		font-family: var(--font-display);
		font-size: 1.25rem;
		font-style: italic;
		font-weight: 600;
		color: var(--accent-bright);
		margin-bottom: 0.5rem;
	}

	.prop-card p {
		font-size: 0.95rem;
		color: var(--ink-soft);
		line-height: 1.6;
		margin: 0;
	}

	.prop-card-soft {
		background: var(--card-soft);
		border-color: rgba(122, 138, 106, 0.2);
	}

	.prop-card-mystic {
		background: linear-gradient(
			135deg,
			var(--card) 0%,
			var(--card-soft) 100%
		);
		border-color: rgba(122, 138, 106, 0.3);
		position: relative;
	}

	.prop-card-mystic .prop-icon {
		color: var(--accent-bright);
	}

	.usage-list {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
		gap: 1rem 2.5rem;
	}

	.usage-item {
		display: flex;
		gap: 1.25rem;
		padding: 1.25rem 0;
		border-bottom: 1px solid rgba(122, 138, 106, 0.08);
	}

	.usage-num {
		font-family: var(--font-display);
		font-size: 1.5rem;
		font-style: italic;
		color: var(--accent-hue);
		flex-shrink: 0;
		min-width: 2.5rem;
	}

	.usage-body h3 {
		font-family: var(--font-display);
		font-size: 1.15rem;
		font-style: italic;
		font-weight: 600;
		color: var(--accent-bright);
		margin-bottom: 0.3rem;
	}

	.usage-body p {
		font-size: 0.93rem;
		color: var(--ink-soft);
		line-height: 1.55;
		margin: 0;
	}

	.warnings-section {
		background: linear-gradient(
			180deg,
			transparent,
			rgba(176, 106, 82, 0.05),
			transparent
		);
	}

	.warning-card {
		display: flex;
		gap: 1rem;
		background: #fdf6f1;
		border: 1px solid rgba(176, 106, 82, 0.22);
		border-left: 3px solid var(--danger);
		border-radius: var(--radius);
		padding: 1.25rem 1.5rem;
	}

	.warning-icon {
		color: var(--danger);
		flex-shrink: 0;
		padding-top: 0.15rem;
	}

	.warning-card h3 {
		font-family: var(--font-display);
		font-size: 1.1rem;
		font-style: italic;
		font-weight: 600;
		color: var(--ink);
		margin-bottom: 0.25rem;
	}

	.warning-card p {
		font-size: 0.92rem;
		color: var(--ink-soft);
		line-height: 1.55;
		margin: 0;
	}

	.info-grid {
		display: grid;
		grid-template-columns: 1fr 1.4fr;
		gap: 1.5rem;
		margin-bottom: 2rem;
	}

	@media (max-width: 760px) {
		.info-grid {
			grid-template-columns: 1fr;
		}
	}

	.storage-card {
		background: var(--card);
		border: 1px solid rgba(170, 145, 60, 0.18);
		border-radius: var(--radius);
		padding: 1.75rem;
	}

	.storage-icon {
		color: var(--accent-hue);
		margin-bottom: 0.75rem;
	}

	.storage-card h3 {
		font-family: var(--font-display);
		font-size: 1.3rem;
		font-style: italic;
		color: var(--accent-bright);
		margin-bottom: 0.5rem;
	}

	.storage-card p {
		color: var(--ink-soft);
		font-size: 0.95rem;
		margin: 0;
		line-height: 1.6;
	}

	.info-card {
		background: var(--card);
		border: 1px solid rgba(122, 138, 106, 0.18);
		border-radius: var(--radius);
		padding: 0.5rem 1.5rem;
		margin: 0;
	}

	.info-row {
		display: flex;
		justify-content: space-between;
		gap: 1rem;
		padding: 1rem 0;
		border-bottom: 1px solid rgba(122, 138, 106, 0.1);
	}

	.info-row:last-child {
		border-bottom: none;
	}

	.info-row dt {
		font-family: var(--font-display);
		font-style: italic;
		color: var(--ink-muted);
		font-size: 0.95rem;
		margin: 0;
	}

	.info-row dd {
		text-align: right;
		color: var(--ink);
		font-size: 0.95rem;
		margin: 0;
		font-weight: 500;
	}

	.manufacturer {
		background: var(--card-soft);
		border: 1px solid rgba(122, 138, 106, 0.2);
		border-radius: var(--radius);
		padding: 1.5rem 1.75rem;
		text-align: center;
	}

	.manufacturer h3 {
		font-family: var(--font-display);
		font-size: 0.85rem;
		letter-spacing: 0.24em;
		text-transform: uppercase;
		color: var(--accent-hue);
		margin-bottom: 0.75rem;
	}

	.manufacturer p {
		color: var(--ink-soft);
		font-size: 0.95rem;
		line-height: 1.7;
		margin: 0;
	}

	.manufacturer strong {
		color: var(--ink);
		font-weight: 500;
	}
</style>
