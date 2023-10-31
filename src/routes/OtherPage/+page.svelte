<script>
  import { onMount } from "svelte";
  let count = 1;
  let fact = "";
  
  const BASEURLFacts = "https://meowfacts.herokuapp.com";

  onMount(async () => {
    const res = await fetch(`${BASEURLFacts}/?count=${count}`);
    const data = await res.json();
    fact = data.data;
    console.log(fact);
    console.log(count);
  });

  function factprint() {
    count += 1;
    console.log(count);
    onMount(async () => {
      const res = await fetch(`${BASEURLFacts}/?count=${count}`);
      const data = await res.json();
      fact = data.data;
      console.log(fact);
    });
  }
</script>

<div class="button">
  <button class="fact_button" on:click={factprint}>
    Press for cat fact
  </button>
</div>
<div>
  {fact}
</div>

