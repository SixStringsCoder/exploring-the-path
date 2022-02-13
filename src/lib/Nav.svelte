



<!-- Load an icon library to show a hamburger menu (bars) on small screens -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<nav class="topnav" id="topNav">
    <a href="/" class="active">Home</a>
    <a href="#contact">Study</a>
    <a href="#about">About</a>
    <a href="#test" class="icon" onclick={() => console.log("TEST CLICK")}>
      <i class="fa fa-bars"></i>
    </a>
    <a id="coursename">Exploring the ancient path in the Buddha’s own words</a>
</nav>


<style>
  /* nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
  } */

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
  background-color: #04AA6D;
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

</style>