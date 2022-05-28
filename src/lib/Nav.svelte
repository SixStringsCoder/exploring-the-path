<script>
  import { fly } from 'svelte/transition'
  import { suttaData } from '../routes/exploring-the-path/data.js';
  const url = "http://localhost:3000/exploring-the-path/"

  let isOpen = false;
  let subNavOpen = false;

  const handleSubNav = () => subNavOpen ? subNavOpen = false : subNavOpen = true 

// $:console.log(url)  
</script>


<nav class="topnav" id="topNav">
  <div>
    <a href="/exploring-the-path"><h1>Exploring the Path</h1></a>
  </div>
  <div id="menu-cont" on:click={() => isOpen = true}>
    <a href="#menu" class="icon" >
      &#9776; 
    </a>
  </div>
</nav>


{#if isOpen}
  <section id="sidenav" class="sidenav" transition:fly={{x: 500}}>
    <a href="#navfauxlink" class="closebtn" on:click={() => isOpen = false}>&times;</a>
   
    <button class="dropdown-btn">Intro to Pali
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="dropdown-container" id="intro-to-pali"></div>

    <button class="dropdown-btn" on:click={handleSubNav}>Exploring the Path
      <i class="fa fa-caret-down" class:fa-caret-up={subNavOpen}></i>
    </button>
    <div class="dropdown-container" id="exploring-the-path" class:show-submenu={subNavOpen} >
      {#each suttaData as suttaObj}
        <a on:click={() => isOpen = false} href={`${url}${suttaObj.id}`}>
          {suttaObj.id} {suttaObj.engname}
        </a>
      {/each}
    </div>

    <button class="dropdown-btn">Buddhasahassanāmāvali
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="dropdown-container" id="buddhasahassanamavali"></div>
  </section>
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

  h1 {
    margin: 0;
  }

  .topnav .icon {
    display: block;
    float: right;
  }

  /* @media screen and (max-width: 600px) {
    .topnav a:not(:first-child) {display: none;}
    .topnav a.icon {
      float: right;
      display: block;
    }
  } */


/* The side navigation menu */
section.sidenav {
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
  section.sidenav a {
    padding: 8px 8px 8px 32px;
    text-decoration: none;
    font-size: 1.1rem;
    color: #f1f1f1;
    display: block;
    cursor: pointer;
    transition: 0.3s;
  }

  .sidenav a, .dropdown-btn {
    padding: 6px 8px 6px 16px;
    text-decoration: none;
    font-size: 20px;
    color: #818181;
    display: block;
    border: none;
    background: none;
    width:100%;
    text-align: left;
    cursor: pointer;
    outline: none;
  }

  /* On mouse-over */
  .sidenav a:hover, 
  .dropdown-btn:hover {
    color: #f1f1f1;
  }

  .dropdown-container {
    display: none;
    background-color: #262626;
    padding-left: 8px;
  }

  .show-submenu {
    display: block;
  }

  /* Optional: Style the caret down icon */
  .fa-caret-down {
    float: right;
    padding-right: 8px;
  }

  section.sidenav .closebtn {
    position: absolute;
    top: 0;
    left: 0;
    font-size: 36px;
  }


  /* On smaller screens, where height is less than 450px, change the style of the sidenav (less padding and a smaller font size) */
  @media screen and (max-height: 450px) {
    section.sidenav {padding-top: 15px;}
    section.sidenav a {font-size: 18px;}
  } 

</style>