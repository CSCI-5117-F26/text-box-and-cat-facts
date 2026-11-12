<script lang="ts">
  let facts = $state([]);

  async function fetch_fact() {
    try {
      const result = await fetch("https://catfact.ninja/fact")

      if (result.ok) {
        const data = await result.json();
        facts.push(data.fact);
      } else {
        alert("Oh no, failed to get fact.");
      }
    } catch {
      alert("Oh no, super fail.");
    }
  }
</script>

<div>
  <button onclick={() => fetch_fact()}>Get a cat fact!</button>
  <ul>
    {#each facts as fact}
      <li>{fact}</li>
    {/each}
  </ul>
</div>
