<script>
    import { suttaData } from './exploring-the-path/data.js'
    const url = "http://localhost:3000/"

</script>

<svelte:head>
  <title>Pariyatti Learning Center</title>
</svelte:head>


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