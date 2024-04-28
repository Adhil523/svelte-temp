<script>
  import { getContext } from "svelte";

  export let username
      const username2=getContext("username-context")
  </script>
  
  <h1>Component F {username}</h1>
  <h1>Context API Data - {username2}</h1>
  