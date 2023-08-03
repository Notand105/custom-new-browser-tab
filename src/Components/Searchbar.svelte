<script>
    let query = ''
    let url = 'https://www.google.com/search?q='
    const search = () =>{
        if(query.length > 0) window.open(url + query)
        query = ''
    }

</script>

<section class=" flex justify-center">
    <div>
        <input bind:value={query} type="text" name="" class="border border-black rounded shadow-lg p-2 " />
        <button on:click={search}  class="bg-zinc-600 hover:bg-zinc-500 rounded p-2 text-white" type="submit">Lupa</button>
    </div>
</section>

