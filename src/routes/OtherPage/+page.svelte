<script>
  let count = 1;
  let fact = "";

  const BASEURLFacts = "https://meowfacts.herokuapp.com";

  const api = async () => {
    const res = await fetch(`${BASEURLFacts}/?count=${count}`);
    const data = await res.json();
    fact = data.data;
    console.log(fact);
  };

</script>

<div class="button">
  <button class="fact_button" on:click={api}> Press for cat fact </button>
</div>
<div>
  {#each fact as facts}
    <p>
      {facts}
    </p>
  {/each}
</div>
