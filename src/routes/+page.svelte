<script lang="ts">
	import { onMount } from "svelte";
	import { fade, fly } from "svelte/transition";
     let ready: boolean = false;
     const placeholders = [
        "A cat playing chess with a unicorn",
        "Spongebob surfing a lava sea",
        "A penguin riding a flamingo through space",
        "A taco eating a burrito",
        "A banana playing the saxophone",
        "A robot having a tea party with dinosaurs",
        "A wizard riding a unicycle on a rainbow",
        "A giraffe wearing sunglasses driving a convertible",
        "A flying pig delivering mail",
        "A dancing potato with a top hat"
    ];

     onMount(() => {
        ready = true;
     });
</script>


{#if ready}
<div class="w-screen h-screen flex flex-col items-center justify-center gap-4 p-8">
    <h1 transition:fly={{delay: 100, opacity: 0, y: 50}} class="font-mono text-7xl glow font-black p-2 select-none">glow</h1>
    <h1 transition:fly={{delay: 200, opacity: 0, y: 50}} class="max-w-lg text-center select-none">An <b>open-source</b> text-to-image tool, write something down here and look at the magic!</h1>
    <div class="w-full max-w-3xl flex flex-row gap-2">
        <input transition:fly={{delay: 300, opacity: 0, y: 50}} type="text" placeholder={placeholders[Math.floor(Math.random() * placeholders.length)] + "..."} class="dark:bg-gray-900 shadow-xl p-4 w-full rounded-full outline-none">
        <button transition:fly={{delay: 300, opacity: 0, y: 50}} class="w-44 bg-indigo-600 text-white rounded-full select-none transition duration-75 cursor-default active:bg-indigo-400  hover:bg-indigo-500"><i class="fa-solid fa-wand-magic-sparkles text-white"></i></button>
    </div>
</div>
{/if}