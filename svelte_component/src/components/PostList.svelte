<script>
    import {onMount} from 'svelte'
    let posts=[]
    onMount(async ()=>{
        const response = await fetch("https://jsonplaceholder.typicode.com/posts")
        posts=await response.json()
        console.log(posts)
    })
</script>

{#each posts as post}
    {#if post.id==3}
    <h3>{post.id} - {post.title} </h3>
    <h4>{post.body}</h4>
    {/if}
    {post.title}
{:else}   
    <p>Loading...</p>
{/each}