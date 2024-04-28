<script>
    import {createEventDispatcher} from 'svelte'
    const dispatcher=createEventDispatcher()
    const data={
        id:1,
        name:"Adhil"
    }
</script>

<h1>
    This is a popup
</h1>
<button on:click={()=>dispatcher('closed',data)}>Close popup</button>