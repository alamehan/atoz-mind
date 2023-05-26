<script setup>
import LearnUXToday from "./tab/LearnUXToday.vue";
import DesignThinkingToolbox from "./tab/DesignThinkingToolbox.vue";
import GoogleUXDesign from "./tab/GoogleUXDesign.vue";

import { ref } from "vue";
const tab = ref("tab_1"); // TAB YANG AKTIF (SELECTED) PERTAMA KALI
</script>

<template>
	<q-card style="min-height: 100dvh"> <!-- Satuan dvh lebih akurat dibandingkan vh -->
		<q-tabs v-model="tab" dense class="text-grey" active-color="primary" indicator-color="primary" align="justify">
			<q-tab name="tab_1" label="Learn UX Today" />
			<q-tab name="tab_2" label="Design Thinking Toolbox" />
			<q-tab name="tab_3" label="Google UX Design" />
		</q-tabs>

		<q-separator />

		<q-tab-panels v-model="tab">
			<q-tab-panel name="tab_1" class="no-padding">
				<LearnUXToday />
			</q-tab-panel>

			<q-tab-panel name="tab_2" class="no-padding">
				<DesignThinkingToolbox />
			</q-tab-panel>

			<q-tab-panel name="tab_3" class="no-padding">
				<GoogleUXDesign />
			</q-tab-panel>
		</q-tab-panels>
	</q-card>
</template>