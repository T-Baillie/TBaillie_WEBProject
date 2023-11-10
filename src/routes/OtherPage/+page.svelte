<script>
  let count = 1;
  let fact = "";

  const BASEURLFacts = "https://meowfacts.herokuapp.com";
    // basic fetch to get cat fact from an api
  const api = async () => {
    const res = await fetch(`${BASEURLFacts}/?count=${count}`);
    const data = await res.json();
    fact = data.data;
  };

</script>
<!-- button code that pushes a cat fact to the screen, then displays in a for each -->
<div class="button">
  <button class="fact_button" on:click={api}> Press for cat fact </button>
</div>
<div class = "fact_display">
  {#each fact as facts}
    
      {facts}
    
  {/each}
</div>
