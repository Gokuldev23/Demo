<script>
  import Update from "./sub-pages/Update.svelte";



</script>




<div class="md:h-screen relative h-fit overflow-hidden w-full overflow-x-hidden pt-[60px]  bg-cover bg-center" style="background-image: url(/news-bg.svg);">
    <div class="md:h-full h-auto flex md:flex-row flex-col items-center">
        <h1 class="md:text-[96px]/[120px]  self-start text-[34px] md:self-end font-[Poppins] h-fit ml-4 md:ml-64 mb-8  md:mb-28 font-bold text-white uppercase origin-left rotate-0 md:-rotate-90 ">
            NEWS & <br class="hidden md:block">UPDATES
        </h1>
        <div class="w-full">
            <Update/>
        </div>
    </div>

    <div class="w-[520px] h-[520px] rounded-full blur-[400px] bg-[#DD00B8] absolute md:-bottom-4 -bottom-1/2 md:-left-4 left-full"></div>
</div>