<script>
  const BASEURLFacts = "https://meowfacts.herokuapp.com";
  let count = 1;
  let fact = [];
  import { onMount } from "svelte";

  onMount(async () => {
    const res = await fetch(`${BASEURLFacts}/?count${count}`);
    let data = await res.json();
    fact = data.data;
    console.log(fact);
  });

  function factprint() {
    count += 1;
    console.log(count);
}
</script>

<div class="button">
    <button class="fact_button" onclick={factprint}> Press for cat fact </button>
</div>
<div class = "fact_display">
    {fact}
</div>
