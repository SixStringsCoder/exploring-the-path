<script>
	import { suttaData } from '../data.js'
	import Header from '$lib/Header.svelte'
	import Introduction from './Introduction.svelte'
	import English from './English.svelte'
	import Compare from './Compare.svelte'
	import Pali from './Pali.svelte'
	import Flashcards from './Flashcards.svelte'
	import AudioPlayer from './AudioPlayer.svelte';
	
	// Loads the ETP lesson
	let index = 0;
	$: selectedSutta = suttaData[index]
	
	// Loads the component
	const webpages = [
		{ name: "Introduction", component: Introduction },
		{ name: "English", component: English },
		{ name: "Pali", component: Pali },
		{ name: "Compare", component: Compare},
		{ name: "Flashcards", component: Flashcards}
	];
	
	let selectedPage = webpages[0];
	let selectBtn = "Introduction"
	
	const handleClick = (e) => {
		selectedPage = webpages[Number(e.target.dataset.index)]
		selectBtn = e.target.textContent
	}
// $:	console.log(selectBtn, selectedPage.name)
</script>

<Header id={selectedSutta.id} 
				paliname={selectedSutta.paliname} 
				engname={selectedSutta.engname}
				meaning={selectedSutta.definition}
				hiLiteSel={selectBtn}
				on:click={handleClick} />

<section>
	{#if selectBtn === "Pali" || selectBtn === "Compare"}
		<AudioPlayer audioLink={selectedSutta.paliaudio} />
	{/if}
	
	<svelte:component this={selectedPage.component} />
</section>
	
	
<style>
	section {
		padding: 0 0 10px 0;
	}
</style>