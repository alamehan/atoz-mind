<script setup>
import TemplateTab from "./tab/TemplateTab.vue";
import { ref } from "vue";
const tab = ref("tab__a"); // TAB YANG AKTIF (SELECTED) PERTAMA KALI
</script>

<template>
	<q-card style="min-height: 100vh">
		<q-tabs v-model="tab" dense class="text-grey" active-color="primary" indicator-color="primary" align="justify">
			<q-tab name="tab__a" label="Ini tab a" />
			<q-tab name="tab__b" label="Ini tab b" />
			<q-tab name="tab__c" label="Ini tab c" />
		</q-tabs>

		<q-separator />

		<q-tab-panels v-model="tab">
			<q-tab-panel name="tab__a" class="no-padding">
				<TemplateTab />
			</q-tab-panel>

			<q-tab-panel name="tab__b" class="no-padding">
				<TemplateTab />
			</q-tab-panel>

			<q-tab-panel name="tab__c" class="no-padding">
				<TemplateTab />
			</q-tab-panel>
		</q-tab-panels>
	</q-card>
</template>