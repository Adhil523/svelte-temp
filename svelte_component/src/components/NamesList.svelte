<script>
  const names=  [
  { firstname: 'John', lastname: 'Doe' },
  { firstname: 'Jane', lastname: 'Smith' },
  { firstname: 'Michael', lastname: 'Johnson' },
  { firstname: 'Emily', lastname: 'Williams' }
];
</script>

{#each names as name}
    <slot name="personname" firstname={name.firstname} lastname={name.lastname}></slot>
{/each}