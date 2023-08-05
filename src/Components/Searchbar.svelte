<script>
    let query = 'buscar...'
    let first_focus = false
    let url = 'https://www.google.com/search?q='

    const foc = () =>{
       if(!first_focus){
        query = ''
        first_focus = true
       } 
    } 

    const search = (e) =>{
        e.preventDefault()
        if(query.length > 0) window.open(url + query)
    }

</script>

<section class=" flex justify-center w-full container mx-auto ">
    <form on:submit={search} class="flex flex-row border-zinc-700 w-4/5 px-4 gap-2">
        <input on:focus={foc} bind:value={query}  type="text" name="" class="flex-1 text-zinc-600 px-4 rounded-full border border-zinc-600  shadow-lg p-2 " />
        <button on:click={search}  class="bg-zinc-600 rounded-full hover:bg-zinc-500 p-2 text-white" type="submit"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M9.5 16q-2.725 0-4.612-1.888T3 9.5q0-2.725 1.888-4.612T9.5 3q2.725 0 4.612 1.888T16 9.5q0 1.1-.35 2.075T14.7 13.3l5.6 5.6q.275.275.275.7t-.275.7q-.275.275-.7.275t-.7-.275l-5.6-5.6q-.75.6-1.725.95T9.5 16Zm0-2q1.875 0 3.188-1.313T14 9.5q0-1.875-1.313-3.188T9.5 5Q7.625 5 6.312 6.313T5 9.5q0 1.875 1.313 3.188T9.5 14Z"/></svg></button>
    </form>
</section>

