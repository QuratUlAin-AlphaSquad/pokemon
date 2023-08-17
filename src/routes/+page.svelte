<script>
    import { pokemon } from "../stores/pokestore";
    import "../app.css";
    import PokemanCard from "../components/pokemanCard.svelte";
    // import module from '../components';

    // console.log($pokemon);

    let searchTerm = "";
    let filterdPokemon = [];

    $: {
        console.log(searchTerm);
        if(searchTerm){
            filterdPokemon = $pokemon.filter(pokeman => pokeman.name.toLowerCase().includes(searchTerm.toLowerCase()));
        }else{
            filterdPokemon = [...$pokemon]
        }
    }
</script>

<svelte:head>
    <title>SvelteKit Pokedex</title>
</svelte:head>

<h1 class="text-2xl text-center my-8 uppercase bg-slate-500">
    SvelteKit Pokedex
</h1>

<input  class="w-full rounded-md text-lg p-4 border-2 border-gray-200" bind:value={searchTerm} type="text" placeholder="Search Pokemon"/>

<div  class="py-4 grid gap-4 md:grid-cols-2 grid-cols-1">

{#each filterdPokemon as pokeman}
    <PokemanCard {pokeman} />

{/each}


</div>






