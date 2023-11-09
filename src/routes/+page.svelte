<script>
  import { onMount } from "svelte";

  let imgs = [];
  const BASE_URL = "https://api.unsplash.com";

  onMount(async () => {
    const res = await fetch
    (`
    ${BASE_URL}/search/photos?query=pets&per_page=3&color=blue&orientation=portrait&client_id=7EFeIv8qjanpMATe8ge5S-Bt6PBIeyUYwzcblESBly4
    `);
    let data = await res.json();
    imgs = data.results;
  });
</script>

<div class="home">
  <div class="heading">
    <h2>Adoption and Co</h2>
  </div>

  <div class="desc">
    <p>
      we value all manner of pets, Here we can you adopt a pet, but we also have
      a store to find anything you may need in order keep them happy and feed!!!
    </p>
  </div>

  <div class="row">
    {#each imgs as img}
      <img src={img.urls.regular} alt="FrontPagePics" />
    {/each}
  </div>

  <div class="titles">
    <div>
      <h1>Adoption Page</h1>
      <a href="/AdoptPage" target="_blank">go here, for the adopt page</a>
    </div>
    <div>
      <h1>Donate Page</h1>
      <a href="/DonatePage" target="_blank">go here, for the Donate page</a>
    </div>
    <div>
      <h1>Other Page</h1>
      <a href="OtherPage" target="_blank">go here, for the other pages</a>
    </div>
  </div>
</div>
