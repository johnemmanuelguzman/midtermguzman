<script setup>
const programs = [
	{
		number: "01",
		short: "CS",
		name: "Computer Science",
		description:
			"Go deeper into computing, from intelligent software to the systems and ideas shaping what comes next.",
		href: "https://ccs.cpu.edu.ph/computer-science/",
		logo: "CSS_PNG-300x300.png",
		color: "coral",
	},
	{
		number: "02",
		short: "IT",
		name: "Information Technology",
		description:
			"Connect people and organizations with the technology that helps them work, grow, and thrive.",
		href: "https://ccs.cpu.edu.ph/information-technology/",
		logo: "1-300x300.png",
		color: "blue",
	},
	{
		number: "03",
		short: "DMIA",
		name: "Digital Media & Interactive Arts",
		description:
			"Bring stories and ideas to life through creative practice and emerging digital media.",
		href: "https://ccs.cpu.edu.ph/digital-media-and-interactive-arts/",
		logo: "MIDAS_PNG-300x300.png",
		color: "yellow",
	},
	{
		number: "04",
		short: "BLIS",
		name: "Library & Information Science",
		description:
			"Make knowledge more useful, accessible, and meaningful for every kind of community.",
		href: "https://ccs.cpu.edu.ph/library-information-science/",
		logo: "LISSO-300x300.png",
		color: "green",
	},
];
</script>

<template>
	<section id="programs" class="programs-section section-pad">
		<div class="section-heading">
			<div>
				<p class="eyebrow"><span></span> Explore our degrees</p>
				<h2>Programs<br /><em>offered.</em></h2>
			</div>
			<p class="section-intro">
				Four distinct paths. One community of people who are ready to learn,
				make, and meet the future with purpose.
			</p>
		</div>

		<div class="program-grid">
			<a
				v-for="program in programs"
				:key="program.short"
				class="program-card"
				:class="`tone-${program.color}`"
				:href="program.href"
				target="_blank"
				rel="noreferrer"
			>
				<div class="program-top">
					<span>{{ program.number }} / 04</span>
					<span class="program-arrow" aria-hidden="true">↗</span>
				</div>
				<div class="program-identity">
					<img
						class="program-logo"
						:src="`https://ccs.cpu.edu.ph/wp-content/uploads/2021/11/${program.logo}`"
						:alt="`${program.name} logo`"
						loading="lazy"
					/>
					<span class="program-monogram">{{ program.short }}</span>
				</div>
				<div class="program-bottom">
					<h3>{{ program.name }}</h3>
					<p>{{ program.description }}</p>
					<span class="text-link">Explore program <b aria-hidden="true">→</b></span>
				</div>
			</a>
		</div>
	</section>
</template>

<style scoped>
.programs-section {
	padding-top: 119px;
	padding-bottom: 128px;
}

.section-heading {
	display: flex;
	justify-content: space-between;
	align-items: end;
}

.section-heading .eyebrow {
	margin-bottom: 24px;
}

.section-heading h2 {
	font-size: clamp(49px, 5.8vw, 74px);
	line-height: 0.99;
}

.section-heading h2 em {
	color: var(--red);
}

.section-intro {
	width: min(340px, 35%);
	margin: 0 0 7px;
	color: var(--muted);
	font-size: 14px;
	line-height: 1.75;
}

.program-grid {
	display: grid;
	grid-template-columns: repeat(4, minmax(0, 1fr));
	gap: 12px;
	margin-top: 56px;
}

.program-card {
	min-height: 351px;
	padding: 20px 21px 22px;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	border: 1px solid var(--line);
	transition: transform 0.25s, box-shadow 0.25s;
}

.program-card:hover {
	z-index: 1;
	transform: translateY(-5px);
	box-shadow: 0 13px 25px rgba(23, 26, 24, 0.1);
}

.tone-coral {
	background: #e5e5e5;
}

.tone-blue {
	background: #d8d8d8;
}

.tone-yellow {
	background: #eeeeee;
}

.tone-green {
	background: #cecece;
}

.program-top {
	display: flex;
	justify-content: space-between;
	color: #5d615b;
	font-family: var(--mono);
	font-size: 9px;
	letter-spacing: 0.05em;
}

.program-arrow {
	font-size: 18px;
	transition: transform 0.2s;
}

.program-card:hover .program-arrow {
	transform: translate(2px, -2px);
}

.program-identity {
	display: flex;
	align-items: center;
	gap: 14px;
}

.program-logo {
	width: 72px;
	height: 72px;
	object-fit: contain;
	mix-blend-mode: multiply;
}

.program-monogram {
	font-family: var(--display);
	font-size: 43px;
	font-weight: 700;
	letter-spacing: -0.07em;
}

.program-bottom h3 {
	min-height: 48px;
	max-width: 230px;
	margin: 0 0 9px;
	font-family: var(--display);
	font-size: 18px;
	font-weight: 700;
	letter-spacing: -0.035em;
	line-height: 1.2;
}

.program-bottom p {
	min-height: 69px;
	margin: 0 0 18px;
	color: #5c5e59;
	font-size: 11px;
	line-height: 1.55;
}

.program-card:hover .text-link b {
	transform: translateX(4px);
}

@media (max-width: 900px) {
	.program-grid {
		grid-template-columns: repeat(2, minmax(0, 1fr));
	}

	.program-card {
		min-height: 300px;
	}
}

@media (max-width: 640px) {
	.programs-section {
		padding-top: 82px;
		padding-bottom: 82px;
	}

	.section-heading {
		align-items: flex-start;
		flex-direction: column;
		gap: 23px;
	}

	.section-heading h2 {
		font-size: 55px;
	}

	.section-intro {
		width: min(100%, 360px);
		font-size: 13px;
	}

	.program-grid {
		gap: 8px;
		margin-top: 33px;
	}

	.program-card {
		min-height: 292px;
		padding: 15px 13px 17px;
	}

	.program-logo {
		width: 58px;
		height: 58px;
	}

	.program-monogram {
		font-size: 34px;
	}

	.program-bottom h3 {
		min-height: 43px;
		font-size: 15px;
	}

	.program-bottom p {
		min-height: 89px;
		font-size: 10px;
	}

	.programs-section .text-link {
		gap: 9px;
		font-size: 10px;
	}
}

@media (max-width: 480px) {
	.program-grid {
		grid-template-columns: 1fr;
	}

	.program-card {
		min-height: 250px;
		padding: 18px;
	}

	.program-bottom h3,
	.program-bottom p {
		min-height: 0;
	}
}
</style>
