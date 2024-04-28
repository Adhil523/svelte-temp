<script>
	let firstname="Bruce"
	let lastname="Wayne"
	$: fullname = `${firstname} ${lastname}`
	let fullname2=`${firstname} ${lastname}`
	const handleClick=()=>{    //to see difference between reactive declaration and normal declarartion
		firstname="Harry"
	}
	let items=[
		{id:1,title:"Mouse",price:250},
		{id:2,title:"Keyboard",price:350},
		{id:3,title:"Pad",price:125},
	]

	$:total=items.reduce((total,curr)=>(total=total+curr.price),0)

	const additem=()=>{
		items=[...items,{id:4,title:"Keys",price:150}]

		console.log(items)
		}

	$: console.log(total)

	let volume=0

	$:{
		if(volume<0){
			alert("Volume can't go lower")
			volume=0
		}
		else if(volume>20){
			alert("Volume can't go higher")
			volume=20
		}
	}
</script>

<main>
	<div id="volume">
		<button on:click={()=>{volume+=2}}>
			Increase Volume
		</button>
		<h2>{volume}</h2>
		<button on:click={()=>{volume-=2}}>
			Decrease Volume
		</button>
	</div>
	<button on:click={handleClick}>Change</button>
	<button on:click={additem}>Add</button>
	<h1>{firstname}  {lastname}</h1>
	<h1>{fullname}</h1>
	<h1>{fullname2}</h1>
	<h1>Total - {total}</h1>
</main>

<style>
	#volume{
		display: flex;
	}
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

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>