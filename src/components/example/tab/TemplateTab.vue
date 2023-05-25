<!-- 
  Catatan template: Setiap tab konten (misal tab__a / tab__b / tab__c) perlu disesuaikan lagi simbol X nya, terdiri dari:
  - Title__X
  - data__X
  - nilai__X
  - defaultNode__X
  - toggleNode__X
  - selected__X
  - expanded__X

  Pro Tips agar source code mudah dibaca: 
  - Fold tag <script agar fokus ngoding di <template
  - Gunakan fitur CTRL+SHIFT+P lalu ketik Fold All/Unfold All/Fold Level 7, pilih sesuai kebutuhan
  - Atau select salah satu tag misal <q-tab-panel, lalu CTRL+SHIFT+P, ketik "Fold All Regions Except Selected"
  - Install extension "Comment Anchor", lalu gunakan (di tab kiri VS Code) untuk navigasi cepat ke konten
-->

<script setup>
import { ref } from "vue";

// 1️⃣ SETUP SEARCH FILTER
const filter = ref("");
const filterRef = ref(null);

function resetFilter() {
	filter.value = "";
	filterRef.value.focus();
}

// 2️⃣ ATUR NODE YANG TERBUKA PERTAMA KALI
let nilai__X = ref(["Title__X", "Subtitle 1"]);

// 3️⃣ ATUR DEFAULT NODE YANG TERBUKA (SAMA SEPERTI DI ATAS)
function defaultNode__X(pohon) {
	let node = ["Title__X", "Subtitle 1"];
	// console.log(node)
	setTimeout(() => {
		pohon.tree.collapseAll();
	}, 100);
	setTimeout(() => {
		pohon.tree.setExpanded(node[0], true);
	}, 100);
	setTimeout(() => {
		pohon.tree.setExpanded(node[1], true);
	}, 100);
	setTimeout(() => {
		pohon.tree.setExpanded(node[2], true);
	}, 100);
}

// 4️⃣ GUNAKAN TOGGLE UNTUK NODE TERTENTU (JIKA DIPERLUKAN)
function toggleNode__X(nilai) {
	let node = "Title__X";
	nilai.tree.isExpanded(node) === true ? nilai.tree.setExpanded(node, false) : nilai.tree.setExpanded(node, true);
}

// 5️⃣ SETUP LAINNYA

const splitterModel = ref(50); // SPLIT MULAI DARI 50%
const selected__X = ref("Title__X"); // NODE YANG AKTIF (SELECTED) PERTAMA KALI
const expanded__X = ref(nilai__X); // NODE YANG TERBUKA (EXPANDED) PERTAMA KALI

// 6️⃣ DATA KONTEN

const data = [
	{
		label: "Title",
		avatar: "./icons-tree/general/title.png",
		children: [
			{
				label: "Subtitle 1",
				avatar: "./icons-tree/general/subtitle-1.png",
				children: [
					{
						label: "Sub 1-1",
						icon: "sym_r_text_snippet",
					},
					{
						label: "Sub 1-2",
						icon: "sym_r_text_snippet",
					},
				],
			},
			{
				label: "Subtitle 2",
				avatar: "./icons-tree/general/subtitle-2.png",
				children: [
					{
						label: "Sub 2-1",
						icon: "sym_r_text_snippet",
					},
					{
						label: "Sub 2-2",
						icon: "sym_r_text_snippet",
					},
				],
			},
			{
				label: "Subtitle 3",
				avatar: "./icons-tree/general/subtitle-3.png",
			},
		],
	},
];

// 7️⃣ PROPS (JIKA DIPERLUKAN)
defineProps({
	msg: String,
});
</script>

<template>
	<q-splitter v-model="splitterModel" style="height: 89.5vh">
		<!-- -------------------------------------------------------------------------- -->
		<!--                              👉 KONTEN KIRI 👈                             -->
		<!-- -------------------------------------------------------------------------- -->

		<template v-slot:before>
			<div class="q-pa-md">
				<!-- ------------------------------ SEARCH FILTER ----------------------------- -->

				<q-input ref="filterRef" filled v-model="filter" label="Search here" class="q-mb-md">
					<template v-slot:append>
						<q-icon v-if="filter !== ''" name="clear" class="cursor-pointer" @click="resetFilter"></q-icon>
					</template>
				</q-input>

				<!-- ------------------------------- ALERT INFO ------------------------------- -->

				<q-banner inline-actions rounded class="bg-primary text-white q-mb-md"> Resource: <a href="#" style="color: white">Resource Title Here</a> | May 2023 </q-banner>

				<!-- ------------------------------ BUTTON FILTER ----------------------------- -->

				<div class="q-gutter-sm q-mt-sm q-mb-md">
					<q-btn outline color="primary" label="Expand All" icon-right="sym_r_open_in_full" @click="$refs.tree.expandAll()"> </q-btn>
					<q-btn outline color="primary" label="Collapse All" icon-right="sym_r_close_fullscreen" @click="$refs.tree.collapseAll()"></q-btn>
					<q-btn outline color="primary" label="Reset" icon-right="sym_r_refresh" @click="defaultNode__X($refs)"></q-btn>
					<!-- <q-btn outline color="primary" label="Toggle" icon-right="sym_r_toggle_on" @click="toggleNode__x($refs)"></q-btn> -->
					<q-btn outline color="primary" label="Home" icon-right="sym_r_home" href="#/"></q-btn>
				</div>

				<!-- ------------------------------ TREE CONTENT ------------------------------ -->
				<q-tree :nodes="data__X" node-key="label" ref="tree" selected-color="primary" v-model:selected="selected__X" v-model:expanded="expanded__X" :filter="filter" default-expand-all="false" dense />
			</div>
		</template>

		<!-- -------------------------------------------------------------------------- -->
		<!--                             👉 KONTEN KANAN 👈                             -->
		<!-- -------------------------------------------------------------------------- -->

		<template v-slot:after>
			<q-tab-panels v-model="selected__X" animated transition-prev="jump-up" transition-next="jump-up">
				<q-tab-panel name="Title__X">
					<!-- ------------------------------ Basic Content ----------------------------- -->
					<h4 class="text-h4 q-mb-md">Title__X</h4>
					<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
					<q-img src="../../../assets/contents/general/landscape.jpg"></q-img>
					<!-- ----------------------------- Quasar Timeline ---------------------------- -->
					<div class="q-px-sm q-py-sm">
						<q-timeline color="primary">
							<q-timeline-entry title="Event Title" subtitle="February 22, 1986">
								<div>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</div>
							</q-timeline-entry>

							<q-timeline-entry title="Event Title" subtitle="February 21, 1986" icon="delete">
								<div>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</div>
							</q-timeline-entry>
						</q-timeline>
					</div>
				</q-tab-panel>

				<!-- ANCHOR SUB-1 -->
				<!-- -------------------------------------------------------------------------- -->
				<!--                                KONTEN SUB-1                                -->
				<!-- -------------------------------------------------------------------------- -->

				<q-tab-panel name="Subtitle 1">
					<div class="text-h4 q-mb-md">Subtitle 1</div>
					<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
				</q-tab-panel>

				<q-tab-panel name="Sub 1-1">
					<div class="text-h4 q-mb-md">Subtitle 1-1</div>
					<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
				</q-tab-panel>

				<q-tab-panel name="Sub 1-2">
					<div class="text-h4 q-mb-md">Subtitle 1-2</div>
					<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
				</q-tab-panel>

				<!-- ANCHOR SUB-2 -->
				<!-- -------------------------------------------------------------------------- -->
				<!--                                KONTEN SUB-2                                -->
				<!-- -------------------------------------------------------------------------- -->

				<q-tab-panel name="Subtitle 2">
					<div class="text-h4 q-mb-md">Subtitle 2</div>
					<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
				</q-tab-panel>

				<!-- ANCHOR SUB-3 -->
				<!-- -------------------------------------------------------------------------- -->
				<!--                                KONTEN SUB-3                                -->
				<!-- -------------------------------------------------------------------------- -->

				<q-tab-panel name="Subtitle 3">
					<div class="text-h4 q-mb-md">Subtitle 3</div>
					<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
				</q-tab-panel>
			</q-tab-panels>
		</template>
	</q-splitter>
</template>
