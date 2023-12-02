<script>
    import { Splide } from '@splidejs/svelte-splide';


</script>



<!-- <main class="relative ">
    <img class="md:w-full w-auto h-[90dvh] md:h-auto object-center object-cover" src="/Hero3 3.svg" alt="">
    <div class="flex md:justify-between md:px-20 px-0 h-full  absolute left-0 top-0 flex-col md:flex-row w-full justify-around items-center ">
        <img class="w-[130px] md:w-[470px] md:h-[525px] h-36" src="/HeroHeader 2.svg" alt="">
        <div></div>
    </div>
</main> -->

<main class="relative  ">
    <!-- <img class="md:w-full w-auto h-[90dvh] md:h-auto object-center object-cover" src="/Hero3 3.svg" alt=""> -->

    <Splide
    options={{
        arrows:false,
        pagination:true
    }}
    >
            {#each Array(3) as item,i}
                <li class="splide__slide relative">
                    <img class="h-screen object-cover object-center md:h-full w-full md:w-full " src="/Hero{i+1}.jpg" alt="">
                    <div class="flex md:justify-between md:px-20 px-0 h-full  absolute left-0 top-0 flex-col md:flex-row w-full justify-around items-center ">
                        <img class=" md:h-[525px] h-36" src="/HeroH{i+1}.png" alt="">
                        <div></div>
                    </div>
                </li>
            {/each}
        </Splide>
        <ul class="splide__pagination fixed bottom-10 z-10" />


</main>


<style>

    .splide__pagination{
        background-color: red;
        position: absolute;
        bottom: 10rem;
        /* width: 20rem; */
    }

</style>