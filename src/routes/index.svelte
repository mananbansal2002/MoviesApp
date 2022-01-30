<!-- 113bdfe7b0a5ebc798ba08338fb456e1 -->

<script context="module">
     export async function load({fetch}){
         const resp=await fetch('https://api.themoviedb.org/3/movie/popular?api_key=113bdfe7b0a5ebc798ba08338fb456e1&language=en-US&page=1');
        const data=await resp.json();
        // console.log(data);
        if(resp.ok){
            return{
                props: {popular: data.results}
            };
        }
     }
</script>


<script>
    import Popularmovies from "../components/popularmovies.svelte";
    export let popular;
    import global from '../global.css'
    console.log(popular)
</script>

<section>
    <Popularmovies {popular}/>
</section>