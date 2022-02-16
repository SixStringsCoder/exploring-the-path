<script>
  import { suttaData } from './data.js'
  const url = "http://localhost:3000/lessons/"

  const loadLesson =(e) => window.open(`${url}${e.target.value}`, '_self')
</script>

<section id="lesson-menu">
    <div>
      <label for="lessons">Quick Link Menu</label>
    </div>
  <select name="lessons" id="lessons" on:change={loadLesson}>
    <option value="" disabled selected>Go to lesson...</option>
    <optgroup label="Chapter 1">
      {#each suttaData as suttaObj}
        <option value={`${suttaObj.id}`}>{`${suttaObj.id} ${suttaObj.paliname}`}</option>
      {/each}
    </optgroup>
    <optgroup label="Chapter 2"></optgroup>
    <optgroup label="Chapter 3"></optgroup>
  </select>
</section>

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
  h1 {
    text-align: center;
    margin: 5px 0;
  }
  
  section#lesson-menu {
    text-align: center;
    margin-top: 10px;
  }  

  label {
    font-size: 1.2rem;
    font-weight: 800;
  }

  select {
    margin: 5px 0;
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

  h3 {
    margin: 5px 0;
  }

  p {
    margin: 8px;
  }
</style>