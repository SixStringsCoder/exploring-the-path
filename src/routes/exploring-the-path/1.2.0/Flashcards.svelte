<script>
	let videoID = "5865413"
  $: videoUrl = `https://quizlet.com/${videoID}/familiarize/embedv2`
</script>

<div>
	<iframe width="100%" title="vocabluary flashcards" scrolling="no" height="400" style="border: 0pt none;" src={videoUrl}></iframe>
</div>
<p style="text-align:center">
	<a href="https://learning.pariyatti.org/draftfile.php/8/user/draft/527845036/1.1.1_Flashcards.pdf">
		<button>Download printable flashcards (PDF)</button>  
	</a>
</p>


<style>
	div {
		background: none repeat scroll 0% 0% rgb(255, 255, 255); padding: 3px;
	}

	button {
		width: 260px;
		padding: 10px;
	}
</style>