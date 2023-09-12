<script>
  import Footer from '$lib/FOOTER.svelte';
  import Header from '$lib/HEADER.svelte';
</script>

<svelte:head>
    <link rel="stylesheet" href="css/main.css">
    <link rel ="stylesheet" href ="css/nav.css">
</svelte:head>

<Header />
<slot />
<Footer />