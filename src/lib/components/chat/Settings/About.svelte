<script lang="ts">
	import { getOllamaVersion } from '$lib/apis/ollama';
	import { WEBUI_NAME, WEB_UI_VERSION } from '$lib/constants';
	import { config } from '$lib/stores';
	import { onMount } from 'svelte';

	let ollamaVersion = '';
	onMount(async () => {
		ollamaVersion = await getOllamaVersion(localStorage.token).catch((error) => {
			return '';
		});
	});
</script>

<div class="flex flex-col h-full justify-between space-y-3 text-sm mb-6">
	<div class=" space-y-3">
		<div>
			<div class=" mb-2.5 text-sm font-medium">{WEBUI_NAME} Version</div>
			<div class="flex w-full">
				<div class="flex-1 text-xs text-gray-700 dark:text-gray-200">
					{WEB_UI_VERSION}
				</div>
			</div>
		</div>

		<hr class=" dark:border-gray-700" />

		<div>
			<div class=" mb-2.5 text-sm font-medium">Ollama Version</div>
			<div class="flex w-full">
				<div class="flex-1 text-xs text-gray-700 dark:text-gray-200">
					{ollamaVersion ?? 'N/A'}
				</div>
			</div>
		</div>

		<hr class=" dark:border-gray-700" />

		<div class="flex space-x-1">
			<a href="https://discord.gg/5rJgQTnV4s" target="_blank">
				<img
					alt="Discord"
					src="https://img.shields.io/badge/Discord-Open_WebUI-blue?logo=discord&logoColor=white"
				/>
			</a>

			<a href="https://twitter.com/OpenWebUI" target="_blank">
				<img
					alt="X (formerly Twitter) Follow"
					src="https://img.shields.io/twitter/follow/OpenWebUI"
				/>
			</a>

			<a href="https://github.com/open-webui/open-webui" target="_blank">
				<img
					alt="Github Repo"
					src="https://img.shields.io/github/stars/open-webui/open-webui?style=social&label=Star us on Github"
				/>
			</a>
		</div>

		<div class="mt-2 text-xs text-gray-400 dark:text-gray-500">
			Created by <a
				class=" text-gray-500 dark:text-gray-300 font-medium"
				href="https://github.com/tjbck"
				target="_blank">Timothy J. Baek</a
			>
		</div>
	</div>
</div>
