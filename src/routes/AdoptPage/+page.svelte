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

function factprint(fact) {
    let test = 10 + 10;
    return test;
}
console.log(test);
</script>

<div class="button">
    <button class="factbutton" on:click={factprint}>
        Press for cat fact
    </button>
</div>
