<script>
	import { fly } from 'svelte/transition';
  let y = 0;
	
	export let audioLink;
	let playerHidden = false;
// $: console.log(playerHidden)
</script>


<svelte:window bind:scrollY={y} />

<section class:fixed={y >= 250}				 
				 transition:fly={{ y: 200, duration: 500 }}>	
	
	<audio controls class:hide={playerHidden}>
		<source src={audioLink} type="audio/mp3">
	Your browser does not support the audio element.
	</audio>
	
	<span class="close" on:click={() => playerHidden != playerHidden}>&times;</span>
</section>	


<style>
	section {
		position: fixed;
		top: 85%;
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: start;
		margin: 10px 0;
	}
	
	audio {
		border: 1px solid black;
		padding: 10px;
		background: black;
	}
	
		audio:before {
		content: "X"
	}
	
	.fixed {
		top: 0;
	}
	
	.hide {
		transform: translateX(200px)
	}
	
	.close {
		color: white;
		background: black;
		font-size: 1.5rem;
		padding: 0 5px;
		font-weight: bold;
	}

	.close:hover,
	.close:focus {
		color: red;
		text-decoration: none;
		cursor: pointer;
	}

</style>