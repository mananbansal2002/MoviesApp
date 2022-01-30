<script>
    export let popular;
    console.log(popular[0]);
    import Moviecard from "./Moviecard.svelte"
</script>

<h2>
    Popular Movies
</h2>
<div class="popular-movies">
{#each popular as movie}

    <Moviecard {movie}/>

{/each}
</div>

<style>
    h2{
        padding:2rem 1rem;
        text-align:center;
    }
    .popular-movies{
        display: grid;
        grid-template-columns: repeat(auto-fit ,minmax(250px,1fr));
        grid-column-gap: 1rem ;
        grid-row-gap: 2rem;
    }
</style>