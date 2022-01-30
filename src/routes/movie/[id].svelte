<!-- 113bdfe7b0a5ebc798ba08338fb456e1 -->

<script context="module">
    export async function load({fetch,params}){
        const resp=await fetch(`https://api.themoviedb.org/3/movie/${params.id}?api_key=113bdfe7b0a5ebc798ba08338fb456e1&language=en-US`);
       const moviedetail=await resp.json();
    //    console.log(data);
       if(resp.ok){
           return{
               props: {moviedetail}
           };
       }
    }
</script>

<script>
    export let moviedetail;

    import Nav from '../../components/nav.svelte'
</script>

<div class="movie-details">
    <Nav/>
    <div class="image-container">
    <img src={'https://image.tmdb.org/t/p/original'+moviedetail.backdrop_path} alt={moviedetail.title}>
    </div>
    <div class="text-container">
        <h1>{moviedetail.title}</h1>
    <p class="details">{moviedetail.overview}</p>
    <p><span>Release Date : </span>{moviedetail.release_date} <br/>
        <span>Budget : </span>{moviedetail.budget}<br/>
        <span>Ratings : </span>{moviedetail.vote_average}<br/>
        <span>Duration : </span>{moviedetail.runtime}mins<br/>
    </p> 
    </div>
</div>

<style>
    h1{
        padding: 1rem 0rem 2rem;
    }
p{
    padding: 1rem 0rem;
}
img{
    width:100%;
    border-radius: 1rem;
}
.movie-details{
margin:2rem 20%;
}
span{
    font-weight: bold;
}


</style>
