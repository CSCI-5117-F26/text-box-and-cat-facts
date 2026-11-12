<script lang="ts">
  let name = $state("Enter Name...");
</script>

<input type="text" bind:value={name} />
{ name }
