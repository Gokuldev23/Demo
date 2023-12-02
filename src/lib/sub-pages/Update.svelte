<script>
    import { Splide } from '@splidejs/svelte-splide';
  import { onMount } from 'svelte';


    let images=[
        {img:'update1.png',text:'The MetaHunt Whitepaper is now live!',badge:'news'},
        {img:'update2.png',text:'The MetaHunt Demo looms closer!',badge:'updates'},
        {img:'update3.jpeg',text:'The MetaHunt Demo looms closer!Learn more about In Game Assets!',badge:''}
    ]
    let carosel;

    onMount(()=>{
        console.log(carosel)
    })
    let currentIndex=1

    function fokul(e){
        carosel.go('>')
    }


</script>




<main class="md:w-3/4 w-full relative">
  <Splide  bind:this={carosel} aria-label="My Favorite Images" options={{
      type:'loop',
      perPage:3,
      height:'auto',
      gap:'20px',
      focus:'center',
      autoplay: true,
      autoWidth:false,
      interval: 8000,
      flickMaxPages: 3,
      updateOnMove: true,
      pagination: false,
      arrows:false,
      padding: '0%',
      throttle: 1000,
      breakpoints:{
        700:{
            perPage:1,
            padding:'25%'
        }
      }}}>

              {#each images as item,i}
              <li class='splide__slide'>
                <div class="md:p-5 p-2 mx-auto md:pb-3 pb-1.5 md:w-[400px] w-[190px] md:h-[514px] h-60 rounded-[20px] md:rounded-[40px] bg-[rgba(255,255,255,0.10)]">
                    <div class="relative">
                        <img src="/{item.img}" class="h-[120px] md:h-full w-full md:w-[364px] rounded-[20px] md:rounded-[40px]" alt="">
                        <span class="uppercase absolute right-5 top-3 bg-gradient-to-r  to-pink-600 from-indigo-700 md:p-[10px] p-1 m-0 rounded-xl md:rounded-[30px] text-[8px]  md:text-base/[18px] text-white font-medium font-[Poppins]">{item.badge}</span>
                    </div>
                    <div class="flex h-[45%]  flex-col justify-between">
                        <p class="md:text-3xl/[34px] text-sm tracking-tight px-1 font-semibold text-white font-[Poppins] capitalize mt-3">{item.text}</p>
                        <p class="md:text-base/[24px] text-[7px] text-white  px-1 tracking-tight font-medium capitalize font-[Poppins]">By The Metahunt Tribune <br>
                            April 9, 2015, 4:00PM
                            </p>
                    </div>
                </div>
              </li>
            
            {/each}
            
          </Splide>
          <div class="w-full md:pt-10 pt-5 mb-5 md:mb-0">
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
    .splide__slide{
      position: relative;
  display: flex;
  align-items: center;
    }

  </style>