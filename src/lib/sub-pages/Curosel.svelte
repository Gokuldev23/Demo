<script>
    import { Splide, SplideSlide } from '@splidejs/svelte-splide';

    // import '@splidejs/svelte-splide/css/core';
    import '@splidejs/svelte-splide/css';
  import { writable } from 'svelte/store';

    let images = ['carousel0', 'carousel1', 'metahunt1'];
    let currentSize='w-64 h-52'
    let currentIndex;

    function onMove(e) {
        currentIndex = e.detail.index;

        console.log(currentIndex)
        // currentSize = `${currentIndex === i ? 'w-96 h-72' : 'w-64 h-52'}`;
    }


</script>

<main class="w-full flex justify-center">
    <Splide class="flex" aria-label="My Favorite Images" on:moved={onMove} hasTrack={true} options={{ gap: '1rem', autoplay: true, arrows: true, perPage: 3, type: 'loop', perMove: 1 }}>
        {#each images as item, i }
            <SplideSlide>
                <img class="{i+1==currentIndex?'w-96':'w-24'}" src="{item}.png" alt="" />
            </SplideSlide>
        {/each}
    </Splide>
</main>


