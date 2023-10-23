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
</script>

<button class ="factbutton">
    Press for cat fact
</button>
<p>{fact}</p>