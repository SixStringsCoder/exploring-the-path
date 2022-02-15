<script>
	export let id;
	export let paliname;
	export let engname;
	export let meaning;
	export let hiLiteSel;
	
	const lessonLinks = ["Introduction", "English", "Pali", "Compare", "Flashcards"];
</script>


<header>
	<p class="pali">
		Namo tassa bhagavato arahato sammāsambuddhassa
	</p>
	<h3>Lesson {id}</h3>
	<h1 title={meaning}>{paliname}</h1>
	<h2>{engname}</h2>	
	
	<nav>
  {#each lessonLinks as linkName, i}
		<button title={linkName}	
						data-index={i} 
						class:highlight={linkName === hiLiteSel}
						on:click>{linkName}</button>
	{/each}
</nav>
</header>	


<style>
	header {
		text-align: center;
		padding: 1rem 0.5rem;
		background-color: #dcd3c0;
	}

	header p.pali {
		text-align: center;
	}
	
	h1, h2, h3 {
		margin: 5px;
	}
	
	h1 {
		font-size: 1.4rem
	}
	h2 {
		font-size: 1.2rem
	}
	h3 {
		font-size: 1rem
	}
	
	p {
		margin: 0;
	}
	
	.pali {
		font-style: italic;
		font-size: .8rem
	}
	
	nav {
		margin: 10px 0 0 0 ;
		padding: 0;
	}
	button {
		border: none;
    border-radius: 5px;
    background: #ba5626;
    font-size: 1rem;
    color: white;
    width: 105px;
		margin: 0 10px;
		cursor: pointer;
	}
	
	.highlight {
		background: #1372BA;
	}
</style>