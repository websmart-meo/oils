<script lang="ts">
	import { base } from '$app/paths';

	type Item = { title: string; text: string };

	const physical: Item[] = [
		{
			title: 'Болеутоляющее действие',
			text: 'Масло гаультерии содержит метилсалицилат — природный аналог аспирина. Это делает его эффективным средством для снятия боли.'
		},
		{
			title: 'Противовоспалительное действие',
			text: 'Помогает уменьшить воспаление и облегчить симптомы ревматизма, артрита и других воспалительных заболеваний.'
		},
		{
			title: 'Антисептические свойства',
			text: 'Масло обладает антисептическими свойствами, что делает его полезным для лечения кожных инфекций и ран.'
		},
		{
			title: 'Жаропонижающее действие',
			text: 'Помогает снизить температуру при лихорадке.'
		},
		{
			title: 'Расслабляющее действие',
			text: 'Помогает расслабить мышцы и снять спазмы, что полезно при мышечных болях и напряжении.'
		}
	];

	const energetic: Item[] = [
		{ title: 'Повышение энергии', text: 'Помогает повысить уровень энергии и бодрости.' },
		{
			title: 'Стимуляция умственной активности',
			text: 'Улучшает концентрацию и ясность ума.'
		},
		{
			title: 'Тонизирующее действие',
			text: 'Повышает работоспособность и улучшает общее состояние.'
		}
	];

	const emotional: Item[] = [
		{ title: 'Снятие стресса и тревоги', text: 'Успокаивает и снижает уровень стресса.' },
		{ title: 'Улучшение настроения', text: 'Способствует созданию позитивного настроя.' },
		{ title: 'Балансировка эмоций', text: 'Помогает обрести внутренний покой и гармонию.' }
	];

	const esoteric: Item[] = [
		{
			title: 'Энергетическое заземление',
			text: 'Соединяет с энергией Земли, создавая устойчивость и гармонию.'
		},
		{
			title: 'Очистка от негативных эмоций',
			text: 'Освобождает от эмоциональных блоков.'
		},
		{
			title: 'Снятие энергетического напряжения',
			text: 'Устраняет блокировки, восстанавливая течение жизненной силы.'
		},
		{
			title: 'Трансформация и исцеление',
			text: 'Способствует личной трансформации и эмоциональному восстановлению.'
		},
		{
			title: 'Стимуляция жизненной энергии',
			text: 'Активизирует корневую чакру.'
		},
		{
			title: 'Защита от энергетических атак',
			text: 'Создаёт защитный барьер от негативного воздействия.'
		}
	];

	const usage: Item[] = [
		{
			title: 'Диффузор',
			text: 'Добавьте 3–5 капель масла в диффузор, чтобы наполнить помещение свежим и бодрящим ароматом.'
		},
		{
			title: 'Аромалампа',
			text: 'Добавьте несколько капель масла в аромалампу с водой для создания расслабляющей атмосферы.'
		},
		{
			title: 'Массажное масло',
			text: 'Смешайте 2–3 капли масла гаультерии с 1 столовой ложкой базового масла (кокосового или миндального) и используйте для массажа. Снимает мышечное напряжение и боль.'
		},
		{
			title: 'Точечный массаж',
			text: 'Нанесите разбавленное масло на определённые точки на теле для облегчения боли и расслабления.'
		},
		{
			title: 'Тёплый компресс',
			text: 'Добавьте 2–3 капли масла в тёплую воду, смочите ткань и приложите к больному месту для снятия воспаления и боли.'
		},
		{
			title: 'Холодный компресс',
			text: 'Используйте холодную воду для уменьшения отёков и воспалений.'
		},
		{
			title: 'Ароматическая ванна',
			text: 'Добавьте 5–10 капель масла в ванну с тёплой водой. Помогает расслабиться и снять мышечное напряжение.'
		},
		{
			title: 'Ножная ванна',
			text: 'Добавьте 2–3 капли масла в тёплую воду и погрузите ноги на 10–15 минут для снятия усталости и боли.'
		},
		{
			title: 'Лечение акне',
			text: 'Смешайте 1 каплю масла гаультерии с 1 чайной ложкой базового масла и нанесите на проблемные участки кожи.'
		},
		{
			title: 'Антисептическое средство',
			text: 'Используйте разбавленное масло для обработки мелких порезов и ран.'
		},
		{
			title: 'Паровые ингаляции',
			text: 'Добавьте 2–3 капли масла в миску с горячей водой, наклонитесь над ней, накрыв голову полотенцем, и вдыхайте пар.'
		},
		{
			title: 'Освежитель воздуха',
			text: 'Добавьте несколько капель масла в воду и распылите в помещении.'
		},
		{
			title: 'Чистящее средство',
			text: 'Масло можно использовать в составе натуральных чистящих средств.'
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
		{ label: 'Латинское название', value: 'Gaultheria procumbens' },
		{ label: 'Состав', value: '100% чистое эфирное масло гаультерии' },
		{ label: 'Объём', value: '10 мл' },
		{ label: 'Способ получения', value: 'Паровая дистилляция' },
		{ label: 'Срок годности', value: '3 года (13.06.2024 — 13.06.2027)' },
		{ label: 'Страна происхождения', value: 'Индия' }
	];
</script>

<svelte:head>
	<title>Эфирное масло гаультерии — Aromatica</title>
	<meta
		name="description"
		content="Эфирное масло гаультерии (Gaultheria procumbens) — свойства, применение, эзотерика, предупреждения и хранение."
	/>
</svelte:head>

<article class="page">
	<header class="hero">
		<a class="back-link" href="{base}/">← Назад к коллекции</a>

		<div class="hero-grid">
			<div class="hero-text">
				<span class="eyebrow">эфирное масло · паровая дистилляция</span>
				<h1>Гаультерия</h1>
				<p class="latin">Gaultheria procumbens</p>
				<p class="lede">
					Природный аналог аспирина — масло, известное своим обезболивающим и противовоспалительным
					действием. Заземляет, очищает энергетику и пробуждает жизненные силы.
				</p>
				<div class="badges">
					<span class="badge">Болеутоляющее</span>
					<span class="badge">Противовоспалительное</span>
					<span class="badge">Заземление</span>
					<span class="badge">10 мл</span>
				</div>
			</div>

			<div class="hero-visual" aria-hidden="true">
				<div class="bottle">
					<div class="bottle-cap"></div>
					<div class="bottle-neck"></div>
					<div class="bottle-body">
						<div class="bottle-label">
							<span>Gaultheria</span>
							<em>procumbens</em>
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
						{#each Array(12) as _, i (i)}
							<g transform="rotate({i * 30})">
								<path
									d="M0 -140c14 18 14 60 0 78-14-18-14-60 0-78ZM0 -115c10 13 10 42 0 55-10-13-10-42 0-55Z"
								/>
							</g>
						{/each}
					</g>
				</svg>
			</div>
		</div>
	</header>

	<section class="section">
		<div class="section-head">
			<span class="section-num">01</span>
			<h2>Свойства</h2>
			<p>Природное действие на тело, подтверждённое многовековой традицией</p>
		</div>
		<div class="cards">
			{#each physical as item (item.title)}
				<div class="prop-card">
					<div class="prop-icon" aria-hidden="true">
						<svg viewBox="0 0 24 24" width="22" height="22">
							<path
								d="M12 2c-2 3-5 5-5 10a5 5 0 0 0 10 0c0-5-3-7-5-10Z"
								fill="none"
								stroke="currentColor"
								stroke-width="1.4"
								stroke-linejoin="round"
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
			<p>Энергетическая работа с тонким телом и чакрами</p>
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
			<p>Тринадцать способов раскрыть масло — от ванны и массажа до точечного нанесения</p>
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

	.hero {
		padding: 2.5rem 0 4rem;
		border-bottom: 1px solid rgba(212, 196, 122, 0.15);
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
		background: rgba(212, 196, 122, 0.14);
		border: 1px solid rgba(212, 196, 122, 0.3);
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

	.mandala {
		position: absolute;
		color: var(--accent);
		z-index: 0;
		animation: rotate 60s linear infinite;
	}

	@keyframes rotate {
		to {
			transform: rotate(360deg);
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
		background: linear-gradient(180deg, #6d6240 0%, #3f3823 100%);
		border-radius: 6px 6px 3px 3px;
		border-top: 1px solid #8a7d52;
	}

	.bottle-neck {
		width: 30px;
		height: 18px;
		background: linear-gradient(180deg, #2a3624 0%, #1d2718 100%);
		border-left: 1px solid rgba(255, 255, 255, 0.05);
		border-right: 1px solid rgba(0, 0, 0, 0.3);
	}

	.bottle-body {
		position: relative;
		width: 130px;
		height: 200px;
		background: linear-gradient(135deg, #2d3b27 0%, #1c241a 60%, #2a3624 100%);
		border-radius: 12px 12px 18px 18px;
		border: 1px solid rgba(255, 255, 255, 0.06);
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
		border: 1px solid rgba(212, 196, 122, 0.5);
		border-radius: 6px;
		background: rgba(0, 0, 0, 0.2);
	}

	.bottle-label span {
		display: block;
		font-size: 1.1rem;
		font-weight: 600;
		letter-spacing: 0.06em;
	}

	.bottle-label em {
		font-size: 0.72rem;
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
		border-bottom: 1px solid rgba(212, 196, 122, 0.1);
	}

	.section:last-of-type {
		border-bottom: none;
	}

	.section-alt {
		background: linear-gradient(180deg, transparent, rgba(212, 196, 122, 0.03), transparent);
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
			rgba(212, 196, 122, 0.05),
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
		border: 1px solid rgba(212, 196, 122, 0.18);
		border-radius: var(--radius);
		padding: 1.5rem;
		transition: all 0.3s ease;
	}

	.prop-card:hover {
		border-color: rgba(212, 196, 122, 0.4);
		transform: translateY(-2px);
		box-shadow: var(--shadow);
	}

	.prop-icon {
		color: var(--accent);
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
		background: rgba(74, 87, 71, 0.5);
		border-color: rgba(212, 196, 122, 0.12);
	}

	.prop-card-mystic {
		background: linear-gradient(
			135deg,
			rgba(74, 87, 71, 0.85) 0%,
			rgba(60, 72, 58, 0.85) 100%
		);
		border-color: rgba(212, 196, 122, 0.25);
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
		border-bottom: 1px solid rgba(212, 196, 122, 0.08);
	}

	.usage-num {
		font-family: var(--font-display);
		font-size: 1.5rem;
		font-style: italic;
		color: var(--accent);
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
			rgba(217, 154, 122, 0.04),
			transparent
		);
	}

	.warning-card {
		display: flex;
		gap: 1rem;
		background: rgba(74, 87, 71, 0.6);
		border: 1px solid rgba(217, 154, 122, 0.25);
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
		border: 1px solid rgba(212, 196, 122, 0.18);
		border-radius: var(--radius);
		padding: 1.75rem;
	}

	.storage-icon {
		color: var(--accent);
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
		border: 1px solid rgba(212, 196, 122, 0.18);
		border-radius: var(--radius);
		padding: 0.5rem 1.5rem;
		margin: 0;
	}

	.info-row {
		display: flex;
		justify-content: space-between;
		gap: 1rem;
		padding: 1rem 0;
		border-bottom: 1px solid rgba(212, 196, 122, 0.1);
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
		background: rgba(74, 87, 71, 0.45);
		border: 1px solid rgba(212, 196, 122, 0.12);
		border-radius: var(--radius);
		padding: 1.5rem 1.75rem;
		text-align: center;
	}

	.manufacturer h3 {
		font-family: var(--font-display);
		font-size: 0.85rem;
		letter-spacing: 0.24em;
		text-transform: uppercase;
		color: var(--accent);
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
