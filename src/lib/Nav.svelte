<script>
  import { fly } from 'svelte/transition'
  import { suttaData } from '../routes/exploring-the-path/data.js';
  const url = "http://localhost:3000/exploring-the-path/"

  let isOpen = false;

// $:console.log(url)  
</script>

<!-- Load an icon library to show a hamburger menu (bars) on small screens -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<nav class="topnav" id="topNav">
  <a href="/" class="active">Home</a>
  <a href="/exploring-the-path">Exploring the Path</a>
  <a href="#buddasahasanamavali">Buddasahasanamavali</a>
  <a href="#test" class="icon" >
    <i class="fa fa-bars" on:click={() => isOpen = true}></i>
  </a>
  <a id="coursename">Exploring the ancient path in the Buddha’s own words</a>
</nav>


{#if isOpen}
  <div id="sidenav" class="sidenav" transition:fly={{x: 300}}>
    <a href="#navfauxlink" class="closebtn" on:click={() => isOpen = false}>&times;</a>
    {#each suttaData as suttaObj}
      <a href={`${url}${suttaObj.id}`}>{suttaObj.id} {suttaObj.engname}</a>
    {/each}
  </div>
{/if}

  

<style>
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
  } 

  .topnav {
    overflow: hidden;
    background-color: #333;
  }

  .topnav a {
    float: left;
    display: block;
    color: #f2f2f2;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
    font-size: 17px;
  }

  .topnav a:hover {
    background-color: #ddd;
    color: black;
  }

  .topnav a.active {
    background-color: #ba5626;
    color: white;
  }

  .topnav .icon {
    display: none;
  }

  @media screen and (max-width: 600px) {
    .topnav a:not(:first-child) {display: none;}
    .topnav a.icon {
      float: right;
      display: block;
    }
  }


/* The side navigation menu */
  div.sidenav {
    height: 100%; /* 100% Full-height */
    width: 300px;
    position: fixed; /* Stay in place */
    z-index: 1; /* Stay on top */
    top: 0; /* Stay at the top */
    right: 0;
    background-color: #111; /* Black*/
    overflow-x: hidden; /* Disable horizontal scroll */
    padding-top: 60px; /* Place content 60px from the top */
    transition: 0.5s; /* 0.5 second transition effect to slide in the sidenav */
  }

  /* The navigation menu links */
  div.sidenav a {
    padding: 8px 8px 8px 32px;
    text-decoration: none;
    font-size: 1.1rem;
    color: #818181;
    display: block;
    cursor: pointer;
    transition: 0.3s;
  }

  /* When you mouse over the navigation links, change their color */
  .sidenav a:hover {
    color: #f1f1f1;
  }

  /* Position and style the close button (top right corner) */
  .sidenav .closebtn {
    position: absolute;
    top: 0;
    left: 0;
    font-size: 36px;
  }

  /* Style page content - use this if you want to push the page content to the right when you open the side navigation */
  #main {
    transition: margin-left .5s;
    padding: 20px;
  }

  /* On smaller screens, where height is less than 450px, change the style of the sidenav (less padding and a smaller font size) */
  @media screen and (max-height: 450px) {
    .sidenav {padding-top: 15px;}
    .sidenav a {font-size: 18px;}
  } 

</style>