<script>
  import ComponentE from "./ComponentE.svelte";
    export let username
    
</script>

<h4>Component C {username}</h4>
<ComponentE username={username}/>

<style>
  h4{
    color: aqua;
  }
</style>