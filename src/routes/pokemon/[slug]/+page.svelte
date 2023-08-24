<!-- <script>

</script> -->
<script>
    import OnMountComponent from "../../../components/OnMountComponent.svelte";
    import { scale } from "svelte/transition";
    // used dummyjson API
    export let data;
    console.log(data);
    const { slug } = data;
</script>

<div class="py-4 grid gap-4 md:grid-cols-3 grid-cols-1" transition:scale>
    <p class="text-lg">{slug.title}</p>
    <p class="text-lg">{slug.description}</p>
    <p class="text-lg">{slug.price}</p>
</div>

<!-- jsonplaceholder API Component -->
<div transition:scale>
    <OnMountComponent />
 
</div>
