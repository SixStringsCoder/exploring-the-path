<script>
	import { fly } from 'svelte/transition';
  let y = 0;
	
	let playerHidden = false;
	$: console.log(playerHidden)
	
	const togglePlayer = () => {
		return playerHidden ? playerHidden = false : playerHidden = true
	}
</script>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<svelte:window bind:scrollY={y} />

{#if !playerHidden}
	<section class:fixed={y >= 250} 
					 transition:fly={{ y: 200, duration: 500 }}>

			<audio controls>
				<source src="https://learning.pariyatti.org/pluginfile.php/183/mod_page/content/4/audio/01%201.1.1%20Bahujanahitasutta.mp3" type="audio/mp3">
			Your browser does not support the audio element.
			</audio>

		<div class="close" on:click={togglePlayer}>&times;</div>
	</section>	
{:else}
	<div id="audio-icon" 
			 transition:fly={{ y: 50, duration: 500 }}
			 on:click={togglePlayer}>
		<i class="fa fa-volume-up" aria-hidden="true"></i>
	</div>
{/if}


<style>
	section {
		position: fixed;
		top: 85%;
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: start;
		margin: 10px 0;
		transition: all 1s;
	}
	
	audio {
		border: 1px solid black;
		padding: 10px;
		background: black;
	}
	
	#audio-icon {
		position: fixed;
		font-size: 1.3rem;
		bottom: 0;
		right: 0;
		background: hsl(41, 29%, 85%);
		border: 1px solid black;
		border-radius: 50%;
		padding: 3px 5px 1px;
		cursor: pointer;
	}
	
	.fixed {
		top: 0;
	}
	
/* 	.hide {
		transform: translateX(-40%)
	} */
	
	.close {
		color: white;
		background: black;
		font-size: 1.5rem;
		padding: 0 5px;
		font-weight: bold;
	}

	.close:hover {
		color: red;
		text-decoration: none;
		cursor: pointer;
	}
	
	.close:active {
		color: green;
	}

</style>