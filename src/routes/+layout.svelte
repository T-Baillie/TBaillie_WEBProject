<script>
  import Header from '$lib/HEADER.svelte';
  import Footer from '$lib/FOOTER.svelte';
</script>

<svelte:head>
    <link rel= "stylesheet" href= "css/main.css">
    <link rel = "stylesheet" href = "css/nav.css">
    <link rel = "stylesheet" href = "css/adopt.css">
</svelte:head>

<Header />

<slot />

<Footer />