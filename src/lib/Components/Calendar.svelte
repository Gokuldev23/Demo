

<script>
    import { Splide } from '@splidejs/svelte-splide';
  import { onDestroy, onMount } from 'svelte';

    let carosel;

    let currentIndex=1
    let addDivider = true;


</script>




<main class="w-full overflow-hidden relative font-[Poppins]  rounded-[28px] px-8 py-4">
    <div class=" md:p-7 border border-[#1CE2F8]  bg-[#291746] rounded-[28px]  shadow-[0px_0px_8px_4px_rgba(182,0,198,0.75)]">
        <h1 class="text-center uppercase font-medium text-xl text-white font-[Kanit] my-4 ">Upcoming Events</h1>
        <div class="  h-fit relative mx-auto">
            <Splide  bind:this={carosel} aria-label="My Favorite Images" options={{
                type: 'loop',
                perPage: 3,
                focus: 'center',
                autoplay: true,
                interval: 5000,
                arrows:false,
                flickMaxPages: 3,
                updateOnMove: true,
                pagination: false,
                padding: '0',
                throttle: 300,
                breakpoints:{
                  700:{
                      perPage:1,
                      padding:''
                  }
                }}}>
          
                        {#each Array(3) as item,i}
                        <li class='splide__slide {currentIndex==i?'is-active':''}'>
                          <div class="">
                              <div id="detail" class=" mx-auto h-full flex items-center">
                                  <img src="/calender{i+1}.png" class="mx-auto self-start" alt="">
                              </div>
                          </div>
                        </li>
                      
                      {/each}
                      
                    </Splide>
        </div>
              <div class="w-full md:mt-24 mt-2 md:hidden block">
                <div class="mx-auto w-fit">
                  <button on:click={()=>carosel.go('<')} class="btn btn-link p-0 w-fit bg-transparent border-0 hover:bg-transparent relative">
                    <img class="md:w-full w-16" src="/arrowBg.svg" alt="">
                    <div class="absolute left-3 md:top-1 top-0 flex justify-center items-center w-full h-full">
                      <img class="md:w-auto w-3" src="/arrow.svg" alt="">
                    </div>
                  </button>
                  <button on:click={()=>carosel.go('>')} class="btn w-fit p-0 bg-transparent border-0 hover:bg-transparent relative">
                    <img class="md:w-full w-16 rotate-180" src="/arrowBg.svg" alt="">
                    <div class="absolute right-3 md:top-1 top-0 flex justify-center items-center w-full h-full">
                      <img class="rotate-180 md:w-auto w-3" src="/arrow.svg" alt="">
                    </div>
                  </button>
                </div>
            </div>
    </div>
</main>


  <style>
    li img{
        /* box-shadow: 0px 6.898px 51.306px 11.21px rgba(143, 0, 255, 0.40); */
        border-radius: 13.797px;
        /* border: 0.862px solid  #EA0070; */
    }

    .splide__slide.is-active{
      /* background-color: red; */
      border: 1px solid #343F48;
      border-top: 0;
      border-bottom: 0;

    }

    li{
    /* height: 80%;
     */
    display: flex;
    justify-content: center;
    }


  </style>