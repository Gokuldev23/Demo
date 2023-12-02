<script>
    import Curosel from './sub-pages/Curosel.svelte';
import Carousel from './sub-pages/Curosel.svelte'
  import Curosel1 from './sub-pages/Curosel1.svelte';
  
</script>


<div class="relative bg-images min-h-screen w-full overflow-x-hidden">
    <!-- <Carousel/> -->
    <!-- <img class="md:w-full w-auto h-screen  md:h-auto object-cover object-center absolute left-0 top-0 -z-10 " src="/section2.svg" alt=""> -->
    <div class="w-[520px] h-[520px] rounded-full bg-[#DD00B8] absolute top-56 -left-40 blur-[446px]"></div>
    <div class=" w-full  font-[Kanit]  text-white md:pt-36 pt-12 flex lg:flex-row flex-col justify-center items-center md:items-start gap-x-4">
        <p  class="  mx-auto uppercase font-bold md:w-1/4 pl-[77px]  w-fit text-3xl md:text-[128px]/[153px]">Fight  to survive</p>
        <div class="flex  items-start pb-6">
                <Curosel1/>
        </div>
    </div>

    <div class="custom font-[Poppins] mt-3 mb-14  md:text-3xl text-xs font-bold pl-4 overflow-x-hidden whitespace-nowrap uppercase flex items-center  w-screen md:h-[90px] h-8 -rotate-2" style="">
        <div class="flex md:gap-x-[51px] gap-x-5 w-fit  custom-animate items-center">
            <div class="flex items-center md:gap-x-4 gap-x-2 ">
                <img class="w-3 h-3 md:w-9 md:h-9" src="/Star 1.svg" alt="">
                <h1>THE ARENA starts NOW</h1>
            </div>
            <div class="flex items-center md:gap-x-4 gap-x-2 ">
                <img class="w-3 h-3 md:w-9 md:h-9" src="/Star 1.svg" alt="">
                <h1>EXPLORE THE LORE</h1>
            </div>
            <div class="flex items-center md:gap-x-4 gap-x-2 ">
                <img class="w-3 h-3 md:w-9 md:h-9" src="/Star 1.svg" alt="">
                <h1>THE ARENA starts NOW</h1>
            </div>
            <div class="flex items-center md:gap-x-4 gap-x-2 ">
                <img class="w-3 h-3 md:w-9 md:h-9" src="/Star 1.svg" alt="">
                <h1>THE ARENA starts NOW</h1>
            </div>
        </div>
    </div>
    <!-- <Curosel1/> -->
    <div class="flex md:pl-9 px-6 pt-11 md:pr-14 pb-24 w-full">
        <div class="flex md:gap-x-8 gap-y-8 md:w-3/4 items-center  md:items-start w-full md:mx-auto md:flex-row flex-col">
            <img class="md:w-[577px] w-[300px] h-[230px]  md:h-[466px]  hover:shadow-[0px_8px_59.5px_13px_rgba(143,0,255,0.44)] transition-all duration-200 object-cover object-center rounded-[20px]" src="/metahunt1.png" alt="">
            <div class="md:w-1/2 w-full md:pr-8 pr-0 text-center md:text-left ">
                <h1 class="md:text-[48px]/[55px] text-3xl uppercase font-bold text-white font-[Poppins]">What is metahunt</h1>
                <p class="my-6 text-base/[30px] md:text-left text-center font-medium font-[Poppins] text-white">
                   <span class="mb-12 block">
                    Welcome to MetaHunt, a high-stakes, web-based game that seamlessly blends survival, strategy, and rewarding gameplay. 
                    Choose from various modes
                   </span> 
                    like Arcade Mode, Skins Skirmish, Token Takedown, and Fortune Frenzy, each offering unique challenges and prizes. Whether you're in it for the thrill of the hunt, the joy of collecting skins, or the ambition to earn cryptocurrency rewards, MetaHunt provides a competitive and exciting battlefield for every type of player. Join now and begin your hunt!
                </p>
                <button class="btn btn-sm md:btn-lg bg-gradient-to-r mt-6 mx-auto md:mx-0 from-pink-600 to-indigo-700 md:py-[14px] md:px-14 px-5 py-1.5 flex items-center justify-center h-fit rounded-[18px]  text-sm/[0] md:text-2xl/[30px] text-white font-semibold font-[Poppins]
                ">Join Us</button>
            </div>
        </div>
    </div>

</div>

<style>
    .custom{
        border: 1px solid #000;
        background: linear-gradient(180deg, rgba(255, 255, 255, 0.08) 0%, rgba(217, 217, 217, 0.04) 100%);
        box-shadow: 0px 4px 20px -1px rgba(0, 0, 0, 0.00);
        backdrop-filter: blur(25px)
    }
    .bg-images{
        background-image: url('/section2.svg');
        background-repeat: no-repeat;
        background-position: center;
        background-size:cover;
        background-attachment: local;
        background-origin: content-box;

        background-position:top;
    }
    .custom-animate{
        animation: scroll 10s linear infinite;
    }
    @keyframes scroll{
        0%{
            transform: translateX(100%);
        }
        100%{
            transform: translateX(-100%);
        }
      
    }


</style>