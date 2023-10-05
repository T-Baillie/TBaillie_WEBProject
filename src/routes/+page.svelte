<script>
    import { onMount } from 'svelte';

    let imgs = [];
    const BASE_URL = "https://api.unsplash.com";
    onMount(() => {
        fetch(`${BASE_URL}/search/photos?query=cats&per_page=3&color=blue&orientation=portrait&client_id=7EFeIv8qjanpMATe8ge5S-Bt6PBIeyUYwzcblESBly4`)
        .then(res => res.json())
        .then(data => {
            imgs = data.results;
        });
    });
</script>

<div class ="home">
    <div class = "heading">   
        <h2>Adoption and Co</h2>
    </div>

    <div class = "front">
        <p> 
            we value all manner of pets, Here we can you adopt a pet, 
            but we also have a store to find anything you may need in order keep them happy and feed!!! 
        </p>
    </div>

    <div class ='row'>
        {#each imgs as img}
            <img src= {img.urls.regular} alt="PetPics"/>
        {/each}
    </div>

    <div class ="titles">
        <div>
            <h1> Adopton Page </h1>
                <a>go here, for the adopt page</a>
        </div>
        <div>    
            <h1> Donate Page </h1>
                <a>go here, for the Donate page</a>
        </div>
        <div>
            <h1> Other Page </h1>
                <a>go here, for the other pages</a>
        </div>
    </div>
</div>





