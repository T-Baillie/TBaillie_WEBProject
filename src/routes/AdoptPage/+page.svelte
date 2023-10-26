<script>
  let imgs = [];
  const BASE_URL = "https://api.unsplash.com";
  import { onMount } from "svelte";

  onMount(async () => {
    const res = await fetch(`
    ${BASE_URL}/search/photos?query=pets&per_page=12&orientation=portrait&client_id=7EFeIv8qjanpMATe8ge5S-Bt6PBIeyUYwzcblESBly4
    `);
    let data = await res.json();
    imgs = data.results;
    console.log(imgs);
  });
</script>

<div class="gallery">
  {#each imgs as img}
    <img src={img.urls.regular} alt="PetPics" />
  {/each}
</div>
