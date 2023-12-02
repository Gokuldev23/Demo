<script>
export let image='sc1'
export let title='Upcoming Events'

</script>



<div class="w-96 pb-9  relative overflow-hidden rounded-b-[10px] rounded-t-2xl font-[Poppins] border border-[#474747] custom bg-gradient-to-b from-[#C118C1] via-transparent  to-transparent">
    <div class="flex justify-between items-center pl-6  ">
        <div class="space-y-2 ">
            <p class="text-3xl font-bold  text-white italic uppercase "> {title}</p>
            <div class="h-2 w-44 rounded-2xl bg-[#FFBF41]"></div>
        </div>
        <img src="/{image}.svg" alt="">
    </div>
    <div class="flex flex-col items-center">
        <div class="w-80 mb-5 rounded-xl h-11 bg-[rgba(255,255,255,0.09)] uppercase text-white font-semibold text-sm font-[Poppins] flex justify-between items-center pl-1 pr-4">
            <div class="bg-gradient-to-l to-[#6B4DFD] from-[#EA0070]  px-5 py-2 rounded-xl">solo</div>
            <div>duo</div>
            <div>squad</div>
            <div>solo fpp</div>
        </div>
        {#each Array(4) as item}
            <div class="w-80 mb-2 rounded-xl  bg-[rgba(255,255,255,0.09)] uppercase text-white font-semibold text-sm font-[Poppins] flex justify-between items-center p-5">
                <div>The MetaDemo</div>
                <div>11.21.23</div>
                <div>4.8</div>
            </div>
        {/each}

    </div>
    
</div>

<style>
    .custom{
        /* background:linear-gradient(180deg, rgba(255, 255, 255, 0.08) 0%, rgba(217, 217, 217, 0.04) 100%); */
        box-shadow: 0px 4px 20px -1px rgba(0, 0, 0, 0.00);
        backdrop-filter: blur(25px);
    }
</style>