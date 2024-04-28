<script>
	import ComponentC from "./components/ComponentC.svelte";
import Greet from "./components/Greet.svelte";
	import {setContext} from 'svelte'
  import Popup from "./components/Popup.svelte";
  import Outer from "./components/Outer.svelte";
	import Card from "./components/Card.svelte";
	import NamesList from "./components/NamesList.svelte";
  import PostList from "./components/PostList.svelte";


	let username="Adhil"
	let username2="Vishvas"
	setContext("username-context",username2)
	let showPopup=false

	const closefunc=(event)=>{
		showPopup=false
		console.log(event.detail)
	}

	function handleGreet(event){
		alert(event.detail)
	}
</script>

<main>
	<Greet name="Bruce"/>
	<ComponentC username={username}/>
	{#if showPopup}
		<Popup on:closed={closefunc}/>
	{/if}
	<button on:click={()=>(showPopup=true)}>Show popup</button>
	<Outer on:greet={handleGreet}/>
	<Card>
		<div slot="header">
			<h3>Header part</h3>
		</div>
		<div slot="content">
			<h3>Content part</h3>
		</div>
		<div slot="footer">
			<h3>Footer part</h3>
		</div>
	</Card>

	<NamesList>
		<h3 slot="personname" let:firstname let:lastname>
			{firstname} , {lastname}

		</h3>
	</NamesList>
	<PostList/>
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

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>