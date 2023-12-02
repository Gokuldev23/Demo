

<script>
  import { fade, slide } from "svelte/transition";


  let isHamburger=false


  function toggle(){
    isHamburger=!isHamburger
  }
</script>


<main class="h-fit md:h-24 md:pb-5 pb-0 md:px-[52px] px-4 w-full  flex items-center relative bg-[#2F0050]">
  <div class="flex items-center  w-full justify-between bg-[#2F0050]">
    <img class="pt-3 pl-2 w-[60px] h-[60px] lg:w-[100px] lg:h-[100px]"  src="/HeroH1.png" alt="">

    <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
    <img on:mousedown={toggle} class="w-6 h-6 md:hidden block" src="/hamburger.svg" alt="">

    {#key isHamburger}
      <ul transition:slide class="uppercase text-white md:relative {isHamburger?`flex h-fit bg-[#2F0050] py-10 gap-y-10 text-lg z-10  absolute left-0 top-0 w-full items-start flex-col mx-0 px-5`:`hidden flex-row`} md:bg-transparent  md:items-center lg:text-lg md:flex-row  md:flex  md:text-base font-bold md:mx-auto md:w-fit lg:gap-x-10 md:gap-x-6">
        <li>info</li>
        <li>marketplace</li>
        <li>news</li>
        <li>mydashboard</li>
        <li>leaderboard</li>
        <li class:hidden={isHamburger}><img class="w-5 h-5" src="/bag.svg" alt=""></li>
        <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
        <li class='absolute right-3 top-5 md:hidden' on:mousedown={toggle} class:hidden={!isHamburger} ><img src="/close.svg" alt=""></li>
      </ul>
    {/key}


    <div id="eclipse" class="w-80 h-80 absolute -left-36 blur-[292px] top-20 rounded-full bg-[#DD00B8]"></div>
  </div>
 
</main>