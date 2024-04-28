<script>
	const num=0
	const names=["Bruce","William","Diana"]
	const new_names=[
		{first:"Bruce",last:"Wayne"},
		{first:"William",last:"Shakespeare"},
		{first:"Diana",last:"Hillary"}
	]
	const formValues={
		name:'',
		country:"",
		remote:false,
		skills:[]
	}
	const handleSubmit=(event)=>{
		event.preventDefault()   //not necessary as event modifier has been used in form
		console.log(event)
		console.log(formValues)

	}
</script>

<main>
	{#if num==0}
		<h1>Number is zero</h1>
	{/if}
	{#each new_names as name,index}
		<h2>
			{index+1}-{name.first} {name.last}
		</h2>
	{/each}
	<form on:submit|preventDefault={handleSubmit}> 
		<div>
			<label for="name">Name</label>
			<input type="text" id="name" bind:value={formValues.name}>
		</div>
		<div>
			<select bind:value={formValues.country}>
				<option value="">Select a country</option>
				<option value="India">India</option>
				<option value="Australia">Australia</option>
				<option value="Japan">Japan</option>
			</select>
		</div>
		<div>
			<input type="checkbox" id="remote" bind:checked={formValues.remote}>
			<label for="remote">Open for remote work</label>
		</div>
		<div>
			<input type="checkbox" value="html" id="html" bind:group={formValues.skills}>
			<label for="html">HTML</label>
			<input type="checkbox" value="css" id="css" bind:group={formValues.skills}>
			<label for="css">CSS</label>
			<input type="checkbox" value="javascript" id="javascript" bind:group={formValues.skills}>
			<label for="javascript">javascript</label>
		</div>
		<div>
			<button>Submit</button>
		</div>
	</form>
	<div>
		<pre>{JSON.stringify(formValues,null,2)}</pre>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}


</style>