

<script>
    import { Splide } from '@splidejs/svelte-splide';
  import { onMount } from 'svelte';


    let images=[
        {img:'syndicate1',text:'Sakura Tech'},
        {img:'syndicate2',text:'Rogue Syndicate'},
        {img:'syndicate3',text:'Sakura Tech'}
    ]
    let carosel;

    let currentIndex=1



</script>




<main class="w-full md:h-[80vh] h-[40vh] relative md:pt-16 pt-8 font-[Poppins] overflow-x-hidden bg-contain bg-center" style="background-image: url(/syndicateBg.jpg);">
    <div class="w-full h-3/4 relative">
        <Splide  bind:this={carosel} aria-label="My Favorite Images" options={{
             type: 'loop',
            perPage: 1,
            focus: 'center',
            autoplay: true,
            interval: 5000,
            arrows:false,
            flickMaxPages: 3,
            updateOnMove: true,
            pagination: false,
            padding: '28%',
            throttle: 300,
            breakpoints:{
              700:{
                  perPage:1,
                  padding:'5%'
              }
            }}}>
      
                    {#each images as item,i}
                    <li class='splide__slide h-full flex items-center {currentIndex==i?'is-active':''}'>
                      <div class="">
                          <div id="detail" class=" mx-auto h-full flex flex-col md:gap-y-4 gap-y-1.5 ">
                            <h1 class="text-center text-white font-bold uppercase"> {item.text}</h1>
                              <img src="/{item.img}.jpeg" class="mx-auto md:h-[30rem] h-44 self-end" alt="">
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
</main>


  <style>
    li img{
        box-shadow: 0px 6.898px 51.306px 11.21px rgba(143, 0, 255, 0.40);
        border-radius: 13.797px;
        border: 0.862px solid var(--Linear, #EA0070);
    }

    li{
    height: 80%;
    display: flex;
    justify-content: center;
    }

    .splide__slide #detail{
        transform: scale(0.7);
        transition: all 0.2s linear;
        align-self:baseline;
    }
    .splide__slide #detail h1{
        font-size: 24px;
        /* margin-bottom: 16px; */
    }
    .splide__slide.is-active #detail{
      transform: scale(1);
      align-self:self-start;
      transform-origin: center center;
    }
    .splide__slide.is-active #detail h1{
      font-size: 48px;
      /* margin-bottom: 56px; */
    }
    @media screen and (max-width:700px){
        .splide__slide.is-active #detail h1{
      font-size: 30px;
      /* margin-bottom: 56px; */
    }
    }

  </style>