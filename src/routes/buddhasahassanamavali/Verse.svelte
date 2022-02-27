<script>
  import { versesData } from './data.js';

  let index = 0;
  $: currentVerse = versesData[index];
  $: vocabWords = currentVerse.vocabulary

  const nextVerse = () => {
    if (index >= versesData.length-1) {
      return index = 0
    }
    return index += 1
  }
  
  const prevVerse = () => {
    if (index <= 0) {
      return index = versesData.length-1
    }
    return index -= 1
  }
</script>

<main>
  <section class="verse">
    <!--TITLE HEADING-->
    <h3>Verse {currentVerse.id}</h3>

    <!--AUDIO-->
    <div class="audio-cont">
      <audio controls>
        <source src={currentVerse.audioURL} type="audio/mp3">      
            Your browser does not support HTML 5 audio.
      </audio>
    </div>

    <!--DEVANAGIRI PALI SCRIPT-->
    <pre class="pali-italics">
      {currentVerse.devapali}
    </pre>

    <!--ROMAN PALI SCRIPT-->
    <pre class="pali-italics">
      {currentVerse.romanpali}
    </pre>

    <!--ENGLISH  TRANSLATION-->
    <pre id="english">
      {currentVerse.engtrans}
    </pre>

     <!-- Next/prev buttons -->
    <span class="prev" on:click={prevVerse}>&#10094;</span>
    <span class="next" on:click={nextVerse}>&#10095;</span>
  </section>

  <hr />
  <section class="pali-vocab">
  <!--PALI VOCABULARY-->
    <h4>Vocabulary</h4>
    <ol>
      {#each vocabWords as wordObj}
        <li><b>{wordObj.word}</b>- {wordObj.definition}</li>    
      {/each}
    </ol>
  </section>

  <section class="quizlet-pdf-cont">
    <!--QUIZLET-->
    <div>
      <iframe src="https://quizlet.com/{currentVerse.quizletID}/flashcards/embed" height="410" width="100%" style="border:0" title="flashcards"></iframe>
    </div>
      
    <!--PDF DOWNLOAD LINK and BUTTON-->
    <div>
      <a href={currentVerse.pdfURL}>
        <button>Download the Flashcards</button>
      </a>
    </div> 
  </section>
</main>


<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: 	hsl(39, 37%, 85%);
  } 

  section {
    padding: 20px;
  }

  section.quizlet-pdf-cont {
    width: 90%;
  }

  .audio-cont {
    margin-left: auto;
    margin-right: auto;
  }

  pre {
    width: 100%;
    text-align: center;
    line-height: 125%;
  }

  pre#english {
    white-space:pre-line;
  }

  .pali-italics {
    font-style: italic;
  }

  .pali-vocab ol {
    max-width: 400px;
  }

  ol {
    margin: 0 0 10px 10px;
  }
  li {
    font-size: 1.1rem;
    line-height: 140%;
  } 

  div {
    width: 100%;
    text-align: center;
  }

  button {
    width: 190px;
    margin-top: 15px;
  }

  /* Next & previous buttons */
  .prev, .next {
    cursor: pointer;
    position: absolute;
    top: 350px; 
    margin: 0 10px;
    padding: 16px;
    color: #888;
    font-weight: bold;
    font-size: 1.5rem;
    user-select: none;
  }

  .prev {
    left: 0;
    border-radius: 0 3px 3px 0;
  }

  /* Position the "next button" to the right */
  .next {
    right: 0;
    border-radius: 3px 0 0 3px;
  }

  /* On hover, add a black background color with a little bit see-through */
  .prev:hover, .next:hover {
    background-color: rgba(0,0,0,0.8);
    color: white;
  }
</style>