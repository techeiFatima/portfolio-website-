<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import Navbar from '$lib/components/Navbar.svelte';
	import '../app.css';
    import { onMount } from 'svelte';

	let { children } = $props();

    let cursorX = 0;
    let cursorY = 0;
    let hovering = false;

    function handleMouseMove(e: MouseEvent) {
        cursorX = e.clientX;
        cursorY = e.clientY;
        
        const target = e.target as HTMLElement;
        if (target.closest('a') || target.closest('button')) {
            hovering = true;
        } else {
            hovering = false;
        }
    }
</script>

<svelte:window onmousemove={handleMouseMove} />

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="noise-overlay"></div>
<div 
    class="custom-cursor" 
    class:hovering 
    style="left: {cursorX}px; top: {cursorY}px;"
></div>

<Navbar />

<main>
	{@render children()}
</main>

