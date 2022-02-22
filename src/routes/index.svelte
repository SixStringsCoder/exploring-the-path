<script>
    import { suttaData } from './exploring-the-path/data.js'
    const url = "http://localhost:3000/exploring-the-path/"
</script>

<svelte:head>
  <title>Exploring the Path</title>
</svelte:head>

<header>
  <h1>Exploring the ancient path in the Buddha’s own words</h1>
</header>

<main class="summary"><div class="no-overflow"> 
  <p>Welcome to <span style="font-weight: bold; font-style: italic;">Exploring the sacred, ancient path in the original words of the Buddha</span> (Exploring the Path).
  </p>
  <p><a href="https://learning.pariyatti.org/pluginfile.php/17/course/section/2/ETP_Table_of_contents_Dec27__2021.pdf?time=1640632154354">Download outline of lessons</a>. Exploring the Path represents a collection of Pāli lessons that are brought to life in bite-sized sections with custom glossaries that allow a new student of the language to quickly delve into some of the most valuable of the Buddha’s teachings right from the beginning of the course.
  </p>
  <p>The approach to learning is one driven by the student’s desire to understand the underlying content. Rather than approaching the Pāli language with a list of vocabulary and linguistic rules, the lessons use custom glossaries to ease the student into the more complex learning tasks. The learning then comes from familiarity rather than memorization. The course aims to keep the student motivated through the unfolding of these ancient texts; learning of the language becomes a natural by-product of the process.
  </p>
  <p>This course aspires to instigate gratitude and faith, by presenting <span style="font-style: italic;">suttas</span> that show the rare opportunity and good fortune to encounter such a path (chapter one); which is the same for each and everyone (chapter two); diving from general statements into detailed expositions of the respective eight components of the Noble Eightfold Path (chapter three); describing the correct practice of <span style="font-style: italic;">dāna</span> and <span style="font-style: italic;">mettā</span> (chapter four); and finally following the tradition of numerical order by portraying those important topics in its last chapter (chapter five) which help the practitioner to move towards liberation.
  </p>
  <p>The lessons that are expected to take a Pāli student somewhere between 20 and 45 minutes to complete. These lessons are intended to be sufficient to keep the student engaged, but not so overwhelming that they can't fit into an already busy schedule.
  </p>
  <p>Some weeks include longer passages than others; all of the lessons will include a Pāli section, written and audio, followed by a customized glossary to help the student work through their own translation of the passage. In addition, there are extensive footnotes that add valuable information regarding the Pāli words themselves, their usage elsewhere in the Tipiṭaka, and other interesting items of note related to the passage or the <span style="font-style: italic;">sutta</span> that is under study. 
  </p>
  <p>There are also English translations available for each lesson. These translations aim to provide a word-for-word translation of the Pāli, so fluency may be sacrificed. Each lesson also provides other learning tools such as flash cards and quizzes. Additionally, the site has discussion forums and an online chat functionality built in -- our hope is that these interactive tools will bring a sense of community to the class and make it more engaging for participants.
  </p>
  <p>Naturally one may work with these at one's own pace, there is no necessity to follow the schedule in which they are posted. Although it is intended that certain repetitions will support the progress of learning the ancient language of Pāli, one may also work at random or simply enjoy the English translations without going into the Pāli.
  </p>
  <p>We welcome you to the course and hope that you find great benefit from what it has to offer.</p>
  <p><span style="font-weight: bold;">Note:</span> To enter in the special Pāli characters using your computer keyboard, you'll need to download and install the <a target="_blank" href="https://www.tipitaka.org/keyboard/">Pāli Keyboard</a>.
  </p>
</main>

<hr />

<h1>Overview of the lessons</h1>
<section id="lesson-cards">
  {#each suttaData as suttaObj, i}
    <div class="card">
      <h3>{`${suttaObj.id} ${suttaObj.paliname}`}</h3>
      <p>{suttaObj.blurb}</p>
      <a href={`${url}${suttaObj.id}`}><button id={`${i}`}>Go to Lesson</button></a>
    </div>
  {/each}
</section>


<style>
  header {
    text-align: center;
  }
  main {
    margin: 2% 5%;
    font-size: 1.4rem;
  }

  .lessons-btn-cont {
    display: flex;
    justify-content: center;
  }

  button {
    width: 130px
  }

  section#lesson-cards {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  h1 {
    text-align: center;
    margin: 5px 0;
  }

  .card {
    width: 80%;
    margin: 10px 0;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 65%);
    padding: 16px;
    text-align: center;
    background-color: hsl(39, 37%, 85%);
    border-radius: 15px;
  }

  h3 {
    margin: 5px 0;
  }

  p {
    margin: 8px;
  }
</style>