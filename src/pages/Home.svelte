
<!-- <h1>enquiries and appointments</h1> -->

<script>
  import Carousel from 'svelte-carousel'
  let changeVue = false ;
  function handleClick() {
		alert('clicked');
    changeVue = true ;
	}
  const images = [
      'https://image.freepik.com/free-vector/pet-shop-sale-banner-with-domestic-animals-dog-cat-zoo-store-flyer-discount-coupon-accessories-toys-supplies-vector-concept-vet-market-parrot-hamster-rabbit_102902-4970.jpg',
      'https://image.freepik.com/free-vector/sale-banner-pet-shop-isometric-with-man-feeding-dog-near-dog-food-rack-with-text_1284-54089.jpg'
  ]




    let newItem = {};
	
    let todoList = [{name: 'Kitty', type:'puppy', status: true},
                    {name: 'Charlie', type:'puppy', status: true},
                    {name: 'Loki', type:'puppy', status: true}];
	
	function addToList() {
		todoList = [...todoList, {name: newItem.name,type:newItem.type, status: false}];
		newItem = {};
	}
	
	function removeFromList(index) {
		todoList.splice(index, 1)
		todoList = todoList;
    }

    // for appointments

    let newApoi = {};
    //selected doctor :
    	let selected;

    let appointmentsList = [
        {medecin: "Dr Jean MARK", date:"11/01/2022", time:"08:00"},
        {medecin: "Dr Marie YAVIS", date:"11/01/2022", time:"08:00"},
        {medecin: "Dr Mathieu SVELTE", date:"11/01/2022", time:"08:00"}
      ];

    function addToAppoiList() {
        console.log(selected)
      	appointmentsList = [...appointmentsList, {medecin: selected, date:newApoi.date, time:newApoi.time}];
		    newApoi = {};
      
    }

    function removeFromApptList(index){
       appointmentsList.splice(index, 1)
		   appointmentsList = appointmentsList;
    }
    

</script>


<center>
<Carousel
  let:loaded
>
  {#each images as img}
    <div class="img-container">
        <img src="{img}" class="img-fluid" alt="promos" />
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
{#if changeVue == false}
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


<br/>
{#each appointmentsList as item, index}
<div class="card">
  <img style="width:15%;"
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
      <li class="list-group-item">{item.date +", "+item.time}</li>
      <!-- <li class="list-group-item">For <i class="fas fa-dog" /></li> -->
      <li class="list-group-item"> <span class="btn btn-danger" on:click={() => removeFromApptList(index)}>Annuler</span></li>
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

<br/>

{#each todoList as item, index}
	<!-- <br/> -->
  <div class="card">
  <img style="width: 20%;"
    src="https://images.unsplash.com/photo-1508292549404-81fd946f8c2e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80"
    class="card-img-top"
    alt="Kitty"
  />
 
  <div class="card-body">
    <!-- <input bind:checked={item.status} type="checkbox"> -->
    <span class:checked={item.status}></span>
    <h5 on:click={handleClick} class="card-title">{item.name}</h5>
    <p class="card-text">{item.type}</p>
    <span on:click={() => removeFromList(index)}>❌</span>
  </div>
</div>
{/each}
{:else}
<h1> is between 5 and 10</h1> 
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
  .card-title {
    cursor: pointer;
  }
</style>
