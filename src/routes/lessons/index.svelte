<script>

  const loadLesson =(e) => {
    const url = "http://localhost:3000/lessons/"
    window.open(`${url}${e.target.value}`, '_self')
  }
</script>

<h1>LESSON HOME PAGE - Long list of lesson links to click</h1>

<section>
  <label for="lessons">Lesson Menu</label>

  <select name="lessons" id="lessons" on:change={loadLesson}>
    <option value="" disabled selected>Select a lesson</option>
    <optgroup label="Chapter 1">
      <option value="1.1.1-Bahujanahitasuttam">1.1.1 Bahujanahitasuttam</option>
      <option value="1.2.0-Dullabho">1.2.0 Dullabho</option>
  </optgroup>
  <optgroup label="Chapter 2">
      
  </optgroup>
  <optgroup label="Chapter 3">
      
    </optgroup>
  </select>
</section>

<style>
  section {
    display: flex;
    justify-content: center;
  }  
</style>