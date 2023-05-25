<template>
	<div class="text-center">
		<div class="retalive-position q-mt-xl q-mb-md">
			<div class="blob" style="margin: 0 auto">
				<img src="../assets/logo-clean-atozmind.svg" />
			</div>
		</div>
		<h6>A collection of mind maps.<br />See the Big Picture 🦅</h6>
		<div class="q-gutter-sm q-mt-md q-mb-xl text-center">
			<q-btn flat rounded style="background: #fce7f3; color: #831843" label="Philosophy" icon="sym_r_psychology_alt" icon-right="sym_r_download" href="https://drive.google.com/drive/folders/1HgjoQuXaDEVG7Ae2lF8-wiMXiceXVDVp"></q-btn><br />
			<q-btn flat rounded style="background: #fce7f3; color: #831843" label="Learn English" icon="sym_r_translate" icon-right="sym_r_download" href="https://drive.google.com/drive/folders/1HgjoQuXaDEVG7Ae2lF8-wiMXiceXVDVp"></q-btn><br />
			<q-btn flat rounded style="background: #fce7f3; color: #831843" label="User Experience (UX)" icon="sym_r_dynamic_form" icon-right="sym_r_chevron_right" href="#/user-experience"></q-btn><br />
			<q-btn flat rounded style="background: #fce7f3; color: #831843" label="Timeline of History" icon="sym_r_history_edu" href="#" disable></q-btn><br />
			<q-btn flat rounded style="background: #fce7f3; color: #831843" label="Academic Disciplines" icon="sym_r_school" href="#" disable></q-btn><br />
			<q-btn flat rounded style="background: #fce7f3; color: #831843" label="Essential Managers" icon="sym_r_groups" href="#" disable></q-btn><br />
			<q-btn flat rounded style="background: #fce7f3; color: #831843" label="Outline of Careers" icon="sym_r_apartment" href="#" disable></q-btn><br />
			<q-btn flat rounded style="background: #fce7f3; color: #831843" label="List of Hobbies" icon="sym_r_interests" href="#" disable></q-btn><br />
		</div>
	</div>
	<div class="fixed-bottom-right q-mr-md q-mb-md">
		<a href="https://alamehan.github.io/" target="_blank">
			<img src="../assets/memoji-alamehan.png" />
		</a>
	</div>
</template>

<style scope>
/* ------------------------ Blob background animation ----------------------- */
/* ----------- Source: https://codepen.io/alvarotrigo/pen/WNggKqz ----------- */

.blob {
	width: 112px;
	height: 112px;
	background: #e15371;
	border-radius: 62% 47% 82% 35% / 45% 45% 80% 66%;
	will-change: border-radius, transform, opacity;
	animation: blobAnimation 5s linear infinite;
	-webkit-animation: blobAnimation 5s linear infinite;
}

@keyframes blobAnimation {
	0%,
	100% {
		border-radius: 42% 58% 70% 30% / 45% 45% 55% 55%;
		transform: translate3d(0, 0, 0) rotateZ(0.01deg);
	}
	34% {
		border-radius: 70% 30% 46% 54% / 30% 29% 71% 70%;
		transform: translate3d(0, 5px, 0) rotateZ(0.01deg);
	}
	50% {
		transform: translate3d(0, 0, 0) rotateZ(0.01deg);
	}
	67% {
		border-radius: 100% 60% 60% 100% / 100% 100% 60% 60%;
		transform: translate3d(0, -3px, 0) rotateZ(0.01deg);
	}
}

/* --------------------------- Beautiful Animation -------------------------- */
/* ----------- Source: https://codepen.io/nelledejones/pen/gOOPWrK ---------- */

.gelatine {
	animation: gelatine 2s infinite;
}

@keyframes gelatine {
	from,
	to {
		transform: scale(1, 1);
	}
	25% {
		transform: scale(0.95, 1.05);
	}
	50% {
		transform: scale(1.05, 0.95);
	}
	75% {
		transform: scale(0.98, 1.02);
	}
}
</style>
