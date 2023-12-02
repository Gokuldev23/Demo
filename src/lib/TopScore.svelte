<script>
  import ScoreCard from "./sub-pages/ScoreCard.svelte";
  import { Splide } from '@splidejs/svelte-splide';


  let events=[{title:'Upcoming Events',image:'sc1'},{title:'LEADERBOARD',image:'sc2'},{title:'LEADERBOARD',image:'sc2'}]
</script>



<main class="relative  bg-center h-[80vh]  overflow-x-hidden flex flex-col  gap-x-6 items-center justify-center bg-no-repeat bg-cover w-full" style="background-image: url(/topScore.svg);">

<h1 class="text-[48px] font-bold font-[Poppins] tracking-tight text-white z-50 uppercase md:absolute relative left-0 w-full mx-auto text-center -top-2">TOP SCORES</h1>

<div class="w-11/12 md:w-fit overflow-x-hidden ">
  <Splide options={{
    arrows:false,
    interval: 8000,
    flickMaxPages: 3,
    updateOnMove: true,
    pagination: false,
    padding: '0%',
    throttle: 1000,
    focus:'center',
    gap:'24px',
    perPage:3,
    breakpoints:{
      700:{
        perPage:1,
        gap:'40px',
        padding:'1%'
      }
    }
  }}>
    {#each events as {title,image}}
  <li class='splide__slide flex justify-center' >
    <ScoreCard {title} {image}/>
  </li>
  {/each}
  </Splide>
</div>
</main>

