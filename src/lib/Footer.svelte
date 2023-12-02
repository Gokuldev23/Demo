<script>
  import EventRoadMap from "./EventRoadMap.svelte";
  import Foot from "./sub-pages/Foot.svelte";
  import Login from "./sub-pages/Login.svelte";



</script>



<main class='min-h-screen overflow-y-hidden bg-no-repeat  w-full '>
    <EventRoadMap/>
    <Login/>
    <!-- <div class="bg-red-700 h-full"> -->
        <Foot/>
    <!-- </div> -->
</main>



<style>
    main{
        background-image: url('/roadmapBg.jpg');
        background-position: center;
        background-size: 100% 100%;

    }

</style>