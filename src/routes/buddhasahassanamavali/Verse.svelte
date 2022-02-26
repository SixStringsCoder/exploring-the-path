<script>
  import { versesData } from './data.js';

  let index = 0;
  let currentVerse = versesData[index];
  $: vocabWords = currentVerse.vocabulary
</script>

<main>
  <section class="verse">
    <!--TITLE HEADING-->
    <h3>Verse {currentVerse.id}</h3>

    <!--AUDIO-->
    <audio controls>
      <source src={currentVerse.audioURL} type="audio/mp3">      
          Your browser does not support HTML 5 audio.
    </audio>

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

  <section>
    <!--QUIZLET-->
    <div class="pdf-download-btn">
      <iframe src="https://quizlet.com/{currentVerse.quizletID}/flashcards/embed" height="410" width="100%" style="border:0"></iframe>
    </div>
      
    <!--PDF DOWNLOAD LINK and BUTTON-->
    <div>
      <a class="btn-pdf" href={currentVerse.pdfURL}>
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
  } 

  section {
    padding: 20px;
  }


  pre {
    line-height: 125%;
  }

  pre#english {
    white-space:pre-line;
  }

  .pali-italics {
    font-style: italic;
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
</style>