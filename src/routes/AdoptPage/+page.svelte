<script>
  let imgs = [];
  let headPic = [];
  const BASE_URL = "https://api.unsplash.com/search/photos?";
  import { onMount } from "svelte";

  onMount(async () => {
    const res = await fetch(`
    ${BASE_URL}query=pets&per_page=12&orientation=portrait&client_id=7EFeIv8qjanpMATe8ge5S-Bt6PBIeyUYwzcblESBly4
    `);
    let data = await res.json();
    imgs = data.results;
    console.log(imgs);
    // const resp = await fetch (`
    // ${BASE_URL}query=house&per_page1&orientation=landscape&client_id=7EFeIv8qjanpMATe8ge5S-Bt6PBIeyUYwzcblESBly4
    // `)
    // let data2 = await resp.json();
    // headPic =data2.results;
    // console.log(headPic);

  });
</script>

<div class="gallery">
  {#each imgs as img}
    <img src={img.urls.regular} alt="PetPics" />
  {/each}
</div>

