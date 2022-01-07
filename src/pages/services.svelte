<script>
	import CollapsibleCard from 'svelte-collapsible-card'
	
	const items = [
		{
			title: 'Wellness Care',
			subtitle: 'I am the first card',
			img: 'https://cdn-icons-png.flaticon.com/512/5572/5572404.png',
			text: 'Our wellness programs include: comprehensive physical exam; internal and external parasite testing.'
		},
		{
			title: 'Vaccination Care',
			subtitle: 'I am the second card',
			img: 'https://cdn-icons-png.flaticon.com/512/2358/2358553.png',
			text: 'When a baby kitten or puppy is born, its immune system is not yet mature; the baby is wide open for infection.'
		},
		{
			title: 'Nutritional Counseling',
			subtitle: 'I am the third card',
			img: 'https://cdn-icons-png.flaticon.com/512/2700/2700478.png',
			text: 'Some pets require special prescription food and all pets benefit from a balanced diet.'
		},
        		{
			title: 'Pain Management',
			subtitle: 'I am the third card',
			img: 'https://cdn-icons-png.flaticon.com/512/1049/1049390.png',
			text: 'We understand that our patients feel pain and discomfort under the same circumstances as people do.'
		}
	]
</script>

<ul>
	
	{ #each items as item }
		<li>
			<CollapsibleCard>
				
				<div slot='header' class='header'>
					<img style="width:50%;height:50%;"src={item.img} alt=""/>
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

</style>