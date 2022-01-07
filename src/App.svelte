<script>
  import Carousel from "./Carousel.svelte";
  import ResultLogin from "./ResultLogin.svelte";
  import Contact from "./pages/contact.svelte";
  import PetAdvice from "./pages/pet_advice.svelte";
  import PetHealth from "./pages/Pet_Health_Plan.svelte";
  import EnquiriesAppointments from "./pages/enquiries_appointments.svelte";
  import Service from "./pages/services.svelte";
  import Home from "./pages/Home.svelte";
   import AppointmentRegistred from "./pages/AppointmentRegistred.svelte";
  import NotFound from "./NotFound.svelte";

  import { Router, Route, Link } from "svelte-navigator";

  const submit = ({ email, password }) =>
    new Promise((resolve, reject) => setTimeout(resolve, 1000));

  export let url = "";
</script>

<Router {url}>
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
	

    <a class="navbar-brand" href="/">
    <img src="https://cdn-icons-png.flaticon.com/512/2138/2138440.png" width="40" height="40" alt="logo">
    La clinique vétérinaire Du Vernais
  </a>
		<div class="collapse navbar-collapse" id="navbarNavDropdown">
		  <ul class="navbar-nav">
        <!-- <li class="nav-item">
          <Link class="nav-link" to="/">Home</Link>
        </li> -->
        <!-- <li class="nav-item">
          <Link class="nav-link" to="login">login</Link>
        </li> -->
        <!-- <li class="nav-item">
          <Link class="nav-link" to="ea">enquiries and appointments</Link>
        </li> -->
		<li class="nav-item">
			<Link class="nav-link" to="php">Pet Health Plan</Link>
		  </li>
        <li class="nav-item">
          <Link class="nav-link" to="pa">Pet Advice</Link>
        </li>
        <li class="nav-item">
          <Link class="nav-link" to="services">Services</Link>
        </li>
        <li class="nav-item">
          <Link class="nav-link" to="contact">Contact us</Link>
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
  <!-- <div class="box"> -->
    <!-- <Route path="/" component={ResultLogin} /> -->
    <Route path="/login" component={ResultLogin} />
    <Route path="/contact"><Contact /></Route>
    <Route path="/pa"><PetAdvice /></Route>
    <Route path="/php"><PetHealth /></Route>
    <Route path="/ea"><EnquiriesAppointments /></Route>
    <Route path="/services"><Service /></Route>
    <Route path="/"><Home /></Route>
    <!-- <Route path="/AppointmentRegistred"><AppointmentRegistred /></Route> -->
  <!-- </div> -->
</Router>
