<script>
  import { onMount } from "svelte";

  let x = 50;
  let y = 50;
  let x_shadow =0;
  let y_shadow = 0;
  let maxHeight = 0;

  const handleMouseMove = (e) => {
    x = e.pageX - window.innerWidth / 2;
    y = e.pageY - window.innerHeight / 2;

    console.log(x,y)
  };

  const handleTitleMouseMove = (e) => {
    let x = e.pageX - window.innerWidth/2 ;
    let y = e.pageY - window.innerHeight*3.8;

    let rad = Math.atan2(y, x).toFixed(2);
    let length = Math.round(Math.sqrt(Math.pow(x, 2) + Math.pow(y, 2)) / 10);

    x_shadow = Math.round(length * Math.cos(rad));
    y_shadow = Math.round(length * Math.sin(rad));
  };

  onMount(() => {
    // document.addEventListener('mousemove', handleMouseMove);
    const title = document.querySelector('.error_title');
    title.addEventListener('mousemove', handleTitleMouseMove);
    // document.querySelector('.btn').addEventListener('click', handleBtnClick);
  });
  let show=false

  // $: titleStyle = `--x: ${x}px; --y: ${y}px; --x-shadow: ${-x_shadow}px; --y-shadow: ${-y_shadow}px;`;
</script>


<svelte:document on:mousemove={handleMouseMove}/>
<section class="top_section"></section>

<section class="error_section" >
  <h2 class="error_section_subtitle ">About our token</h2>
  <div class="content_wrapper">
    <h1 class="error_title md:text-[240px] text-[96px] cursor-pointer"  style="{show?`text-shadow:${x_shadow}px ${y_shadow}px 0.5px #D114E8`:''}" on:mousemove={()=>show=true} on:mouseleave={()=>show=false}>
      <p style="background-position: {x}px {y}px" class="">$MHNT</p>
      $MHNT
    </h1>
    <h2>Tokenomics</h2>
  </div>
  <div class="btn-container">
    <a href="#" class="btn">
      LEARN MORE
    </a>
  </div>
</section>





  <style lang="scss">
    $deep-purple: #3B0257;
$neon-accent: #D114E8;
$light-purple: #7C57A1;
$black: #000000;
$grey: #A0A0A0;
$bright-pink: #FF39C7;
$golden: #FFD700;
$antique-white: #FAEBD7;

$primary-color: $neon-accent;
$secondary-color: $light-purple;
$dark-black: $deep-purple;
$gradient: linear-gradient(to top, $primary-color, $secondary-color);
$black-gradient: linear-gradient(-225deg, $dark-black, $black);
*{margin:0;padding:0;}
a{
  text-decoration: none;
}
section{
  font-family: 'Kanit', sans-serif;
	font-weight: 700;
	// color: $black;
}

.error_section {
  display: flex;
  justify-content: center;
  width: 100%;  // Adjust the width as per your requirement
  margin: 0 auto;  
  height: auto;
  align-items: center;
  flex-direction: column;
  padding: 5px 0;
  background-image: $black-gradient;
  
  &_subtitle {
    color: $neon-accent;
    text-transform: uppercase;
    letter-spacing: 5pt;
    font-weight: 500;
    font-size: 0.8rem;
    margin-top: 30px;
    margin-bottom:1rem;
    text-shadow:1px 1px 10px #f564d8, 1px 1px 10px #ff10db;

  }
	.error_title{
		--x-shadow: 0;
		--y-shadow: 0;
		--x:50%;
		--y:50%;
    color: #3B0257;
		transition: all 0.2s ease;
		position: relative;
    padding: 0rem;
    font-weight: 700;
		&:hover{
			transition: all 0.2s ease;
			text-shadow: var(--x-shadow) var(--y-shadow) 0.5px #D114E8;
		}
    p{
			position: absolute;
			top: 0rem;
			left: 0rem;
			background-image: radial-gradient(circle closest-side, rgba(white, 0.05), transparent);
			// background-position: var(--x) var(--y);
			background-repeat: no-repeat;
			text-shadow: none; 
			background-clip: text;
			-webkit-text-fill-color: transparent;  
			transition: all 0.1s ease;
		  }
	
	}
}
.btn-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.btn{
	padding:10px 20px;
	border-radius: 30px;
	background: linear-gradient(269deg, #EA0070 0.63%, #6B4DFD 99.77%);
	box-shadow: 0px 2px 5px 0px rgba(0,0,0,0.2), inset 0px -2px 5px 0px rgba(0,0,0,0.2);
	border: none;

	cursor: pointer;
  margin-top: 3px;

	// text-shadow: 0px 1px $black;
	color: white;
	text-transform: uppercase;
	letter-spacing: 1.5pt;
	font-family: 'Poppins', sans-serif;
	font-size: 1rem;
  margin-bottom: 20px;
	font-weight: 500;
  transition: all 0.5s ease-in-out;



	&:hover{
		text-shadow: 0px 1px 1px $black;
		transform: translateY(-5px);
		box-shadow: 0px 4px 15px 2px rgba(0,0,0,0.1), inset 0px -3px 7px 0px rgba(0,0,0,0.2);
		transition: ease-out 0.2s all;
	}
}
h2 {
  font-family: 'Kanit','Poppins';
font-size: 32px;
font-style: normal;
font-weight: 500;
line-height: 38.4px;
text-align: center;
margin: 10px 0;
}




  </style>

 