<script>
    export let data;
    console.log(data);
    const { slug } = data
</script>

<h1>{slug.title}</h1>
<p>{slug.description}</p>
<p>{slug.price}</p>