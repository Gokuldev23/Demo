<script>
    // @ts-ignore
    import { Splide } from '@splidejs/svelte-splide';
  import { onMount } from 'svelte';


    let images=['carousel0','carousel1','metahunt1']
    let carosel;

    onMount(()=>{
        let img=document.querySelectorAll('li')

        console.log(img)
        img.src='/update2.jpeg'
    })
    let currentIndex=1

    function asd(e){
      
      updateBackgroundImage()

    }

    let current=0
    function updateBackgroundImage(e) {
      console.log("====Ele====",e.detail.prev)
      current=e.detail.prev

      const element = document.querySelector('.splide__slide.is-active.is-visible');

      let arr=['/frame2.svg','/frame.svg','/frame2.svg']


      element.style.setProperty('--bg-image', `url(${arr[current]})`)

        // let activeElement = document.querySelector('.splide__slide.is-active');
        // let backgroundImage;

        // // Set the background image based on the currentIndex
        // if (currentIndex % 2 === 0) {
        //   backgroundImage = 'url(/update1.png)';
        // } else {
        //   backgroundImage = 'url(/update2.png)';
        // }
        // // Set the background image of the active element
        // activeElement.style.backgroundImage = backgroundImage;
  }
</script>

<main class="w-full ml-auto relative h-fit ">
  <Splide  on:move={updateBackgroundImage} bind:this={carosel} aria-label="My Favorite Images" options={{
      type:'loop',
      perPage:3,
      height:'28rem',
      gap:0,
      focus:'center',
      autoplay: true,
      autoWidth:false,
      interval: 8000,
      // flickMaxPages: 3,
      updateOnMove: true,
      pagination: false,
      arrows:false,
      padding: '0%',
      throttle: 1000,
      breakpoints:{
        950:{
          perPage:2,
          padding:'10%'
        },
        700:{
          perPage:1,
          padding:'20%',
          height:'20rem'
        }
      }}}>
              {#each images as item,i}
              <li  class='splide__slide {currentIndex==i?`is-active `:''}'>

                 <img id="img" src="{item}.png" class="scale-1 rounded-xl " alt=""/>

              </li>
            {/each}
    </Splide>
    <div class="w-full  pt-5 mb-5 md:mb-0 absolute bottom-0">
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
    :root {
  --bg-image: url('/public/frame.svg');
}

    .splide__slide.is-active{
      background-color: transparent;
    }
    .splide__slide img{
          /* width: 250.735px; */
          /* padding: 20px; */
          /* height: 203.479px; */
          transform: scale(0.85);
          border-radius: 10px;
          /* flex-shrink: 0; */
          /* margin:0 auto ; */
          width: 75%;
          height: 60%;
         /* height: 40%; */
          margin: 0 auto;
    }
    .splide__slide{
          position: relative;
      display: flex;
      align-items: center;
    }

    .splide__slide.is-active img{
          transform: scale(1);
          border-radius: 0;
          
          /* position: absolute;
          left: 0;
          top: 5%; */
          /* width: 100%;
          height: 100%;    */
          display: block;
          /* width: 320px; */
          height:62%;     
          /* height: 45%; */
          width: 98%;
          /* width: 95%; */
    }
    .splide__slide.is-active::before{
      content: '';
      position: absolute;
      right: 0;
      bottom: 75px;
      left: 0;
      background-image: var(--bg-image);
      /* background-image: url('/public/frame.svg'); */
      background-size: cover;
      width: 100%;
      height:75%;
      transform: scale(1.02);
      background-repeat: no-repeat;
      background-position:center;
      z-index: 1;
        
    }
    @media screen and (max-width:500px){
      .splide__slide img{
        height: 40%;
      }
      .splide__slide.is-active img{
        height: 45%;
        width: 95%;
      }
      .splide__slide.is-active::before{
        bottom: 50px;
      background-size: contain;
      }

    }
  </style>