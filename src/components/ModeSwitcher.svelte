<script lang="ts">
	import { toggleMode, mode } from 'mode-watcher';
	import { fly } from 'svelte/transition';


	$effect( () => {
		console.log("Applied mode: ", $mode)
	})
</script>

<button aria-label="Mode Switcher" onclick={toggleMode} class="flex flex-row justify-center items-center p-1 cursor-pointer opacity-65 hover:opacity-90 transition-all border-2 border-text rounded-full">
    {#if $mode === "light"}
	<img in:fly={{y: 10}} class="size-5" src="/svg/lamp.svg" alt="Light Mode Switch" />
    {:else}
	<img in:fly={{y: -10}} class="size-5" src="/svg/candle-flame.svg" alt="Dark Mode Switch" />
    {/if}
</button>
