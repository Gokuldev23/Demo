<script>
  import Calendar from "./Components/Calendar.svelte";
  import Events from "./sub-pages/Events.svelte";


</script>



<main class="min-h-screen w-full flex flex-col items-center justify-center pt-16 pb-12 ">
  <h1 class="self-start text-white md:text-[80px]/[90px] md:ml-[70px] ml-5  md:mb-16 mb-12 uppercase text-3xl/[40px] font-[Poppins] font-bold">Events <br>
    &ROADMAPS</h1>
  <div class="flex flex-col-reverse gap-y-8 md:flex-row justify-center items-center md:pr-32 pr-0">
    <Events/>
    <Calendar/>
  </div>
</main>