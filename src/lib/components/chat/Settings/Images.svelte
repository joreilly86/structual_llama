<script lang="ts">
	import toast from 'svelte-french-toast';

	import { createEventDispatcher, onMount } from 'svelte';
	import { config, user } from '$lib/stores';
	import {
		getAUTOMATIC1111Url,
		getDefaultDiffusionModel,
		getDiffusionModels,
		getImageGenerationEnabledStatus,
		toggleImageGenerationEnabledStatus,
		updateAUTOMATIC1111Url,
		updateDefaultDiffusionModel
	} from '$lib/apis/images';
	import { getBackendConfig } from '$lib/apis';
	const dispatch = createEventDispatcher();

	export let saveSettings: Function;

	let loading = false;

	let enableImageGeneration = true;
	let AUTOMATIC1111_BASE_URL = '';

	let selectedModel = '';
	let models = [];

	const getModels = async () => {
		models = await getDiffusionModels(localStorage.token).catch((error) => {
			toast.error(error);
			return null;
		});
		selectedModel = await getDefaultDiffusionModel(localStorage.token);
	};

	const updateAUTOMATIC1111UrlHandler = async () => {
		const res = await updateAUTOMATIC1111Url(localStorage.token, AUTOMATIC1111_BASE_URL).catch(
			(error) => {
				toast.error(error);
				return null;
			}
		);

		if (res) {
			AUTOMATIC1111_BASE_URL = res;

			await getModels();

			if (models) {
				toast.success('Server connection verified');
			}
		} else {
			AUTOMATIC1111_BASE_URL = await getAUTOMATIC1111Url(localStorage.token);
		}
	};

	const toggleImageGeneration = async () => {
		if (AUTOMATIC1111_BASE_URL) {
			enableImageGeneration = await toggleImageGenerationEnabledStatus(localStorage.token).catch(
				(error) => {
					toast.error(error);
					return false;
				}
			);

			if (enableImageGeneration) {
				config.set(await getBackendConfig(localStorage.token));
				getModels();
			}
		} else {
			enableImageGeneration = false;
			toast.error('AUTOMATIC1111_BASE_URL not provided');
		}
	};

	onMount(async () => {
		if ($user.role === 'admin') {
			enableImageGeneration = await getImageGenerationEnabledStatus(localStorage.token);
			AUTOMATIC1111_BASE_URL = await getAUTOMATIC1111Url(localStorage.token);

			if (enableImageGeneration && AUTOMATIC1111_BASE_URL) {
				getModels();
			}
		}
	});
</script>

<form
	class="flex flex-col h-full justify-between space-y-3 text-sm"
	on:submit|preventDefault={async () => {
		loading = true;
		const res = await updateDefaultDiffusionModel(localStorage.token, selectedModel);

		dispatch('save');
		loading = false;
	}}
>
	<div class=" space-y-3 pr-1.5 overflow-y-scroll max-h-80">
		<div>
			<div class=" mb-1 text-sm font-medium">Image Settings</div>

			<div>
				<div class=" py-0.5 flex w-full justify-between">
					<div class=" self-center text-xs font-medium">Image Generation (Experimental)</div>

					<button
						class="p-1 px-3 text-xs flex rounded transition"
						on:click={() => {
							toggleImageGeneration();
						}}
						type="button"
					>
						{#if enableImageGeneration === true}
							<span class="ml-2 self-center">On</span>
						{:else}
							<span class="ml-2 self-center">Off</span>
						{/if}
					</button>
				</div>
			</div>
		</div>
		<hr class=" dark:border-gray-700" />

		<div class=" mb-2.5 text-sm font-medium">AUTOMATIC1111 Base URL</div>
		<div class="flex w-full">
			<div class="flex-1 mr-2">
				<input
					class="w-full rounded py-2 px-4 text-sm dark:text-gray-300 dark:bg-gray-800 outline-none"
					placeholder="Enter URL (e.g. http://127.0.0.1:7860/)"
					bind:value={AUTOMATIC1111_BASE_URL}
				/>
			</div>
			<button
				class="px-3 bg-gray-200 hover:bg-gray-300 dark:bg-gray-600 dark:hover:bg-gray-700 rounded transition"
				type="button"
				on:click={() => {
					// updateOllamaAPIUrlHandler();

					updateAUTOMATIC1111UrlHandler();
				}}
			>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					viewBox="0 0 20 20"
					fill="currentColor"
					class="w-4 h-4"
				>
					<path
						fill-rule="evenodd"
						d="M15.312 11.424a5.5 5.5 0 01-9.201 2.466l-.312-.311h2.433a.75.75 0 000-1.5H3.989a.75.75 0 00-.75.75v4.242a.75.75 0 001.5 0v-2.43l.31.31a7 7 0 0011.712-3.138.75.75 0 00-1.449-.39zm1.23-3.723a.75.75 0 00.219-.53V2.929a.75.75 0 00-1.5 0V5.36l-.31-.31A7 7 0 003.239 8.188a.75.75 0 101.448.389A5.5 5.5 0 0113.89 6.11l.311.31h-2.432a.75.75 0 000 1.5h4.243a.75.75 0 00.53-.219z"
						clip-rule="evenodd"
					/>
				</svg>
			</button>
		</div>

		<div class="mt-2 text-xs text-gray-400 dark:text-gray-500">
			Include `--api` flag when running stable-diffusion-webui
			<a
				class=" text-gray-300 font-medium"
				href="https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/3734"
				target="_blank"
			>
				(e.g. `sh webui.sh --api`)
			</a>
		</div>

		{#if enableImageGeneration}
			<hr class=" dark:border-gray-700" />

			<div>
				<div class=" mb-2.5 text-sm font-medium">Set default model</div>
				<div class="flex w-full">
					<div class="flex-1 mr-2">
						<select
							class="w-full rounded py-2 px-4 text-sm dark:text-gray-300 dark:bg-gray-800 outline-none"
							bind:value={selectedModel}
							placeholder="Select a model"
						>
							{#if !selectedModel}
								<option value="" disabled selected>Select a model</option>
							{/if}
							{#each models as model}
								<option value={model.title} class="bg-gray-100 dark:bg-gray-700"
									>{model.model_name}</option
								>
							{/each}
						</select>
					</div>
				</div>
			</div>
		{/if}
	</div>

	<div class="flex justify-end pt-3 text-sm font-medium">
		<button
			class=" px-4 py-2 bg-emerald-600 hover:bg-emerald-700 text-gray-100 transition rounded flex flex-row space-x-1 items-center {loading
				? ' cursor-not-allowed'
				: ''}"
			type="submit"
			disabled={loading}
		>
			Save

			{#if loading}
				<div class="ml-2 self-center">
					<svg
						class=" w-4 h-4"
						viewBox="0 0 24 24"
						fill="currentColor"
						xmlns="http://www.w3.org/2000/svg"
						><style>
							.spinner_ajPY {
								transform-origin: center;
								animation: spinner_AtaB 0.75s infinite linear;
							}
							@keyframes spinner_AtaB {
								100% {
									transform: rotate(360deg);
								}
							}
						</style><path
							d="M12,1A11,11,0,1,0,23,12,11,11,0,0,0,12,1Zm0,19a8,8,0,1,1,8-8A8,8,0,0,1,12,20Z"
							opacity=".25"
						/><path
							d="M10.14,1.16a11,11,0,0,0-9,8.92A1.59,1.59,0,0,0,2.46,12,1.52,1.52,0,0,0,4.11,10.7a8,8,0,0,1,6.66-6.61A1.42,1.42,0,0,0,12,2.69h0A1.57,1.57,0,0,0,10.14,1.16Z"
							class="spinner_ajPY"
						/></svg
					>
				</div>
			{/if}
		</button>
	</div>
</form>
