<script>

	import CollapsibleCard from 'svelte-collapsible-card'
	
	const items = [
		{
			title: 'Availablity',
			subtitle: 'I am the first card',
			img: 'https://www.doctolib.fr/webpack/e293c03bd4b367efb62c.svg',
			text: 'Quickly access the availability of all the pet healthcare professionals'
		},
		{
			title: 'Accessibility',
			subtitle: 'I am the second card',
			img: 'https://www.doctolib.fr/webpack/414f6d548cd8e7420ec2.svg',
			text: 'Make informed decisions tailored to your health needs'
		},
		{
			title: 'Professionalism',
			subtitle: 'I am the third card',
			img: 'https://www.doctolib.fr/webpack/27df8684b01bff357f01.svg',
			text: 'Find the appointment history and medical documents and Receive automatic reminders by SMS or email.'
		}
	]

</script>

<ul>
	
	{ #each items as item }
		<li>
			<CollapsibleCard>
				
				<div slot='header' class='header'>
					<img src={item.img} alt=""/>
					<div class='titles'>
						<h2>{ item.title }</h2>
						<p>{ item.text }</p>
					</div>
				</div>
				
			
			</CollapsibleCard>
		</li>
	{ /each }

</ul>

<style>

	ul {
		list-style: none;
		padding: 0;
		margin: 0 auto;
		width: 90%;
		max-width: 900px;
		color: rgb(50,50,50);
		font-size: 1.1rem;
	}
	
	li {
		margin-bottom: 0em;
		border-bottom: 1px solid rgb(200,200,200);
	}
	
	.header {
		padding: 0.5em;
		display: flex;
	}
	
	img {
		display: block;
		border-radius: 5px;
	}
	
	.titles {
		padding: 0 0 0 1em;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
	
	h2 {
		margin: 0;
		width: 100%;
	}
	
	p {
		margin: 0;
	}
	
	.body {
		padding: 0.5em;
	}
</style>