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
  <nav class="navbar navbar-expand-md bg-dark navbar-dark">
    <a class="navbar-brand" href="/">
      <img
        src="https://cdn-icons-png.flaticon.com/512/2138/2138440.png"
        width="40"
        height="40"
        alt="logo"
      /></a
    >
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#collapsibleNavbar"
    >
      <span class="navbar-toggler-icon" />
    </button>
    <div class="collapse navbar-collapse" id="collapsibleNavbar">
      <ul class="navbar-nav">
        <li class="nav-item">
          <Link class="nav-link" to="login">login</Link>
        </li>
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
      </ul>
    </div>
  </nav>

  <Route path="/login" component={ResultLogin} />
  <Route path="/contact"><Contact /></Route>
  <Route path="/pa"><PetAdvice /></Route>
  <Route path="/php"><PetHealth /></Route>
  <Route path="/ea"><EnquiriesAppointments /></Route>
  <Route path="/services"><Service /></Route>
  <Route path="/"><Home /></Route>
</Router>
