<script>
    import { suttaData } from './exploring-the-path/data.js'
    const url = "http://localhost:3000/"

    const courses = [
      {
        name: "Introduction to Pali",
        descr: "This is a short introduction to Pāli utilizing audio, video, crossword puzzles, Quizlet flashcards and activities to learn Pāli.",
        subdir: "introduction-to-pali"
       },
       {
         name: "Exploring the Path - Pali Course",
        descr: "This course will explore Pāli texts that provide guidance and inspiration for those walking on the Path.",
        subdir: "exploring-the-path"
       }, 
       {
         name: "Buddhasahassanāmāvali",
        descr: "The renowned meditation teacher S.N. Goenka composed and chanted verses to express his gratitude and devotion towards the Buddha—verses called Buddhasahassanāmāvalī. This course uses these verses as a basis for learning Pāli.",
        subdir: "buddhasahassanamavali"
       }
    ];
</script>

<svelte:head>
  <title>Pariyatti Learning Center</title>
</svelte:head>

<header>
  <h1>Pariyatti Learning Center</h1>
</header>

<main class="summary"><div class="no-overflow"> 
  <p>Welcome to the Pariyatti Learning Center. These online Pāli language courses are offered free of charge by <a href="http://www.pariyatti.org">Pariyatti</a></p>
  <p>You may take these courses as a Guest, or create an account to save your progress.</p>
  <p><span style="font-weight: bold;">Note: </span>After you create your account you will need to enroll in the courses in which you wish to participate. To do so, click on the course you are interested in, and then click on the "Enroll me in this course" link on the left side of the page in the Administration panel.</p>
</main>

<hr />


<section id="lesson-cards">
  <h2>Available courses</h2>
  {#each courses as {name, descr, subdir}}
    <div class="card">
      <h3><a href={`${url}${subdir}`}>{name}</a></h3>
      <p>{descr}</p>
    </div>
  {/each}
</section>


<style>
  main {
    margin: 2% 5% 30px;
    font-size: 1.4rem;
  }

  section#lesson-cards {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
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
</style>