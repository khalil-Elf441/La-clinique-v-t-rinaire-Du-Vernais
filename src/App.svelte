

<script>
  import Carousel from "./Carousel.svelte";
  import ResultLogin from "./ResultLogin.svelte";
  import NotFound from './NotFound.svelte';



  import { Router, Route, Link } from "svelte-navigator";

  const submit = ({ email, password }) =>
  new Promise((resolve, reject) => setTimeout(resolve, 1000));

  export let url = "";


</script>

<Router url="{url}">
<nav class="navbar navbar-dark bg-dark">
 <a class="navbar-brand" href="#">
	 CarringPets
 </a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarText" aria-controls="navbarText" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarText">
    <ul class="navbar-nav mr-auto">
	 <li class="nav-item">
    <Link class="nav-link" to="/">Home</Link> 
	 </li>
	 <li class="nav-item">
	<Link class="nav-link" to="login">login</Link>
	 </li>
	<li class="nav-item">
    <Link class="nav-link" to="ea">enquiries and appointments</Link>
	 </li>
	<li class="nav-item">
	<Link class="nav-link" to="pa">Pet Advice</Link>
	 </li>
	<li class="nav-item">
	<Link class="nav-link" to="services">Services</Link>
	 </li>
	<li class="nav-item">
	<Link class="nav-link" to="contact">contact</Link>
	 </li>
	<!-- <li class="nav-item active">
	<Link to="login">login</Link>
	 </li>
	<li class="nav-item active">
    <Link to="cas">spiner</Link>
	</li> -->
	</ul>
	</div>
  </nav>
    <div class="box">
      <Route path="/" component={ResultLogin} />
      <Route path="/login" component={ResultLogin} />
      <Route path="/cas"><Carousel /></Route>
    </div>
  </Router>



