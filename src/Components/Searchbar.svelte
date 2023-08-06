<script>
    let Days = ['Lunes', 'Martes', 'Miercoles', 'Jueves', 'Viernes', 'Sabado', 'Domingo']
    let Months = ['Enero', 'Febrero', 'Marzo','Abril','Mayo', 'Junio', 'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre']
    let query = 'buscar...'
    let first_focus = false
    let url = 'https://www.google.com/search?q='
    let interval
    let hour = new Date()
    $: timeToShow =  hour.getHours() + ':' + hour.getMinutes() + ':' + hour.getSeconds()  
    $: dateToShow = Days[hour.getDate()] + ' ' +  hour.getDay() + ' - ' + Months[hour.getMonth()]
    interval = setInterval(()=>{
        hour = new Date()
    },1000)

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

<section class=" flex flex-col gap-8 w-full mx-auto justify-center h-1/2 ">
    <h2 class="text-5xl text-center text-white">{dateToShow}</h2>
    <h3 class="text-2xl text-center text-white">{timeToShow}</h3>
    <form on:submit={search} class="flex flex-row mx-auto border-zinc-700 w-4/5 px-4 gap-2">
        <input on:focus={foc} bind:value={query}  type="text" name="" class="flex-1 text-zinc-600 px-4 rounded-full border border-zinc-600  shadow-lg p-2 " />
        <button on:click={search}  class="bg-white rounded-full hover:bg-zinc-300 p-2 " type="submit"><img src="https://thenounproject.com/api/private/icons/3101577/edit/?backgroundShape=SQUARE&backgroundShapeColor=%23000000&backgroundShapeOpacity=0&exportSize=752&flipX=false&flipY=false&foregroundColor=%23000000&foregroundOpacity=1&imageFormat=png&rotation=0" alt="search button" width="30px" /></button>
    </form>
</section>

