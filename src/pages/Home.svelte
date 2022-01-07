<!-- <h1>enquiries and appointments</h1> -->
<script>
  import Carousel from "svelte-carousel";

  const images = [
    "https://image.freepik.com/free-vector/pet-shop-sale-banner-with-domestic-animals-dog-cat-zoo-store-flyer-discount-coupon-accessories-toys-supplies-vector-concept-vet-market-parrot-hamster-rabbit_102902-4970.jpg",
    "https://image.freepik.com/free-vector/sale-banner-pet-shop-isometric-with-man-feeding-dog-near-dog-food-rack-with-text_1284-54089.jpg",
  ];

  let changeVue = false;
  function handleClick() {
    // alert('clicked');
    changeVue = true;
  }

  let newItem = {};

  let todoList = [
    { name: "Kitty", type: "Kitten", status: true },
    { name: "Charlie", type: "Kitten", status: true },
    { name: "Loki", type: "Kitten", status: true },
  ];

  function addToList() {
    todoList = [
      ...todoList,
      { name: newItem.name, type: newItem.type, status: false },
    ];
    newItem = {};
  }

  function removeFromList(index) {
    todoList.splice(index, 1);
    todoList = todoList;
  }

  // for appointments

  let newApoi = {};
  //selected doctor :
  let selected;

  let appointmentsList = [
    { medecin: "Dr Lara MARK", date: "11/01/2022", time: "08:00" },
    { medecin: "Dr Marie YAVIS", date: "11/01/2022", time: "08:00" },
    { medecin: "Dr Jolie SVELTE", date: "11/01/2022", time: "08:00" },
  ];

  function addToAppoiList() {
    console.log(selected);
    appointmentsList = [
      ...appointmentsList,
      { medecin: selected, date: newApoi.date, time: newApoi.time },
    ];
    newApoi = {};
  }

  function removeFromApptList(index) {
    appointmentsList.splice(index, 1);
    appointmentsList = appointmentsList;
  }
</script>

{#if changeVue == false}
  <!-- html start -->

  <!-- <img
  style="width: 100%;"
  class="slide-image"
  src="//webdesign-finder.com/fluffy-paw/wp-content/uploads/2016/11/slide-3.png"
  alt="For Your Pets"
/>
<div class="container">
  <div class="col-md-7 inner-wrap">
    <div class="fw-heading-row">
      <h2 class="fw-special-title">
        <small>Providing Special Care </small><br />For Your Pets
      </h2>
    </div>
    <div class="row">
      <p class="fw-desc-row col-sm-10">
        Your pet is in good hands with us! Let your favorite get the best care
        in our center.
      </p>
    </div>
  </div>
</div>
<br /> -->

  <div class="row">
    <div class="card bg-dark text-white border-light">
      <img
        style="width: 100%;"
        class="card-img"
        src="//webdesign-finder.com/fluffy-paw/wp-content/uploads/2016/11/slide-3.png"
        alt="Card image"
      />
      <div class="card-img-overlay">
        <h5 class="card-title text-dark">Providing Special Care</h5>
        <p class="card-text text-dark">For Your Pets</p>
        <p class="card-text text-dark">
          Your pet is in good hands with us! Let your favorite get the best care
          in our center.
        </p>
      </div>
    </div>
  </div>

  <br />
  <br />

  <div class="row">
    <div class="col-sm-6">
      <div class="card border-light">
        <img
          style="width: 80%;"
          src="//webdesign-finder.com/fluffy-paw/wp-content/uploads/2016/11/dog-sleep.png"
          class="card-img-top"
          alt="about"
        />
        <!-- <div class="card-body">
        <h5 class="card-title">Special title treatment</h5>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div> -->
        <!-- 
      <Carousel let:loaded>
        {#each images as img}
          <div class="img-container">
            <img src={img} class="img-fluid" alt="promos" />
          </div>
        {/each}
      </Carousel> -->
      </div>
    </div>
    <div class="col-sm-6">
      <div class="card border-light">
        <div class="card-body">
          <h2 class="card-title">
            About <strong>The Du Vernais veterinary clinic</strong>
          </h2>
          <div class="divider" />
          <p class="card-text">
            The Du Vernais veterinary clinic has 10 veterinarians. It is
            specialized in pets cats, dogs, rodents, reptiles and birds. It does
            not treat farm animals. .
          </p>
        </div>
      </div>
    </div>
  </div>

  <center>
    <Carousel let:loaded>
      {#each images as img}
        <div class="img-container">
          <img style="width:90%;" src={img} class="img-fluid" alt="promos" />
        </div>
      {/each}
    </Carousel>
  </center>

  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css"
  />

  <!-- <input type="text" id="appt" name="appt">
<input type="date" id="appt" name="appt">
<input type="time" id="appt" name="appt"> -->

  <div class="container">
    <div class="input-group">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">Doctor</span>
      </div>
      <!-- <input
    type="text"
    class="form-control"
    placeholder="Doctor"
    aria-label="Doctor"
    bind:value={newApoi.medecin}
    aria-describedby="basic-addon1"
  /> -->

      <select bind:value={selected}>
        {#each appointmentsList as question}
          <option value={question.medecin}>
            {question.medecin}
          </option>
        {/each}
      </select>

      <!-- <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">speciality</span>
  </div>
  <input
    type="date"
    class="form-control"
    placeholder="text"
    aria-label="text"
    bind:value={newApoi.speciality}
    aria-describedby="basic-addon1"
  /> -->

      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">Date</span>
      </div>
      <input
        type="date"
        class="form-control"
        placeholder="Date"
        aria-label="Date"
        bind:value={newApoi.date}
        aria-describedby="basic-addon1"
      />

      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">Time</span>
      </div>
      <input
        type="time"
        class="form-control"
        placeholder="Time"
        aria-label="Time"
        aria-describedby="basic-addon1"
        bind:value={newApoi.time}
        step="600"
        min="07:00"
        max="18:00"
      />
      <!-- <button>Ajouter</button> -->
      <button on:click={addToAppoiList}>Reserver</button>
    </div>

    <h1>Next appointment</h1>

    <br />
    {#each appointmentsList as item, index}
      <div class="card">
        <img
          style="width:15%;"
          src="http://wwsthemes.com/themes/medwise/v1.4/images/doctor-single.jpg"
          class="card-img-top"
          alt="..."
        />
        <div class="card-body">
          <h5 class="card-title">{item.medecin}</h5>
          <p class="card-text">Veterinary Surgery</p>
          <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
        </div>
      </div>
      <div class="card">
        <div class="card-body">
          <ul class="list-group list-group-flush">
            <li class="list-group-item">Date & Time</li>
            <li class="list-group-item">{item.date + ", " + item.time}</li>
            <!-- <li class="list-group-item">For <i class="fas fa-dog" /></li> -->
            <li class="list-group-item">
              <span
                class="btn btn-danger"
                on:click={() => removeFromApptList(index)}>Annuler</span
              >
            </li>
          </ul>
        </div>
      </div>
    {/each}

    <h1>Your registred pets</h1>

    <div class="input-group">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">Name</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="name"
        aria-label="name"
        bind:value={newItem.name}
        aria-describedby="basic-addon1"
      />

      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">type</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="type"
        aria-label="type"
        bind:value={newItem.type}
        aria-describedby="basic-addon1"
      />

      <!-- <button>Ajouter</button> -->
      <button on:click={addToList}>Ajouter</button>
    </div>

    <!-- <input bind:value={newItem.name} type="text" placeholder="new todo item.."> -->
    <!-- <button on:click={addToList}>Add</button> -->

    <br />
    {#each todoList as item, index}
      <!-- <br/> -->
      <div class="card">
        <img
          style="width: 20%;"
          src="https://images.unsplash.com/photo-1508292549404-81fd946f8c2e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80"
          class="card-img-top"
          alt="Kitty"
        />
        <div class="card-body">
          <!-- <input bind:checked={item.status} type="checkbox"> -->
          <span class:checked={item.status} />
          <h5 on:click={handleClick} class="card-title">{item.name}</h5>
          <p class="card-text">{item.type}</p>
          <span on:click={() => removeFromList(index)}>❌</span>
        </div>
      </div>
    {/each}
  </div>
{:else}
  <div class="container">
    <div class="main-body">
      <div class="row">
        <div class="center">
          <div class="card">
            <div class="card-body">
              <div class="d-flex flex-column align-items-center text-center">
                <img
                  src="https://images.unsplash.com/photo-1508292549404-81fd946f8c2e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80"
                  alt="Admin"
                  class="rounded-circle p-1 bg-primary"
                  width="110"
                />
                <div class="mt-3">
                  <h4>Pet details</h4>
                  <p class="text-secondary mb-1">Kitty</p>
                  <p class="text-muted font-size-sm">Avignon France</p>
                </div>
              </div>
              <hr class="my-4" />
              <ul class="list-group list-group-flush">
                <li
                  class="list-group-item d-flex justify-content-between align-items-center flex-wrap"
                >
                  <h6 class="mb-0">
                    <svg
                      xmlns="https://upload.wikimedia.org/wikipedia/commons/b/b5/Vector-kilogram_weight.svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      class="feather feather-globe me-2 icon-inline"
                      ><circle cx="12" cy="12" r="10" /><line
                        x1="2"
                        y1="12"
                        x2="22"
                        y2="12"
                      /><path
                        d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"
                      /></svg
                    >Wight
                  </h6>
                  <span class="text-secondary">5Kg</span>
                </li>
                <li
                  class="list-group-item d-flex justify-content-between align-items-center flex-wrap"
                >
                  <h6 class="mb-0">
                    <svg
                      xmlns="https://u7.uidownload.com/vector/915/221/vector-whippet-race-dog-svg-eps.jpg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      class="feather feather-github me-2 icon-inline"
                      ><path
                        d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
                      /></svg
                    >Race
                  </h6>
                  <span class="text-secondary">Aegean</span>
                </li>
                <li
                  class="list-group-item d-flex justify-content-between align-items-center flex-wrap"
                >
                  <h6 class="mb-0">
                    <svg
                      xmlns="https://www.svgrepo.com/show/139933/circular-line-with-word-age-in-the-center.svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      class="feather feather-twitter me-2 icon-inline text-info"
                      ><path
                        d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"
                      /></svg
                    >Age
                  </h6>
                  <span class="text-secondary">1 Year</span>
                </li>
                <li
                  class="list-group-item d-flex justify-content-between align-items-center flex-wrap"
                >
                  <h6 class="mb-0">
                    <svg
                      xmlns="https://cdn-icons-png.flaticon.com/512/2535/2535759.png"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      class="feather feather-instagram me-2 icon-inline text-danger"
                      ><rect
                        x="2"
                        y="2"
                        width="20"
                        height="20"
                        rx="5"
                        ry="5"
                      /><path
                        d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"
                      /><line x1="17.5" y1="6.5" x2="17.51" y2="6.5" /></svg
                    >Vaccinated
                  </h6>
                  <span class="text-secondary">up to date</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <br />
        <br />
        <br />
        <table class="table table-striped">
          <thead>
            <tr>
              <th scope="col">Vaccin</th>
              <th scope="col">Liora</th>
              <th scope="col">Tiora</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th scope="row">First injection</th>
              <td>✔️</td>
              <td>✔️</td>
            </tr>
            <tr>
              <th scope="row">Second injection</th>
              <td>✔️</td>
              <td>❌</td>
            </tr>
            <tr>
              <th scope="row">Third Injection</th>
              <td>✔️</td>
              <td>❌</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
{/if}

<!-- <div class="card">
  <img
    src="https://images.unsplash.com/photo-1508292549404-81fd946f8c2e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80"
    class="card-img-top"
    alt="Kitty"
  />
  <div class="card-body">
    <h5 class="card-title">Kitty</h5>
    <p class="card-text">Puppy</p>
  </div>
</div> -->
<style>
  .slide-content {
    width: 100%;
  }

  .card {
    flex-direction: row;
  }
  .card img {
    width: 30%;
  }
</style>
