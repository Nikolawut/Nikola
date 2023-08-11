<script lang="ts">
    import { goto } from "$app/navigation";
    import { onMount } from "svelte";
    let data:any = [{fullName:"Avengers: EndGame", description:"Marvel 2019 3h", img:"mov1.jpg", link:"https://goku.sx/watch-movie/watch-avengers-endgame-19722/1092340"},
                    {fullName:"Interstellar",  description:"Legendary Pictures 2014 2h49m", img:"mov2.jpg", link:"https://goku.sx/watch-movie/watch-interstellar-19788/933928"},
                    {fullName:"The Imitation Game", description:"Black Bear Pictures 2014 1h54m", img:"mov3.jpg",link:"https://goku.sx/watch-movie/watch-the-imitation-game-19720/933974"},
                    {fullName:"Iron Man", description:"Marvel 2008 2h06m", img:"mov4.jpg",link:"https://goku.sx/movie/watch-iron-man-19680"}                  ]

    let skills:any = [{name:"JS", progress:"70%", value:"70", color:"white"},
                      {name:"Svelte", progress:"40%", value:"40", color:"orange"},
                      {name:"Html", progress:"90%", value:"90",color:"blue"},
                      {name:"CSS", progress:"80%", value:"80",color:"yellow"}]    
 
let secondElement: HTMLElement | null = null;
$: scrollToSecond = () => {
  if (secondElement) {
    secondElement.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }
};

onMount(() => {
  secondElement = document.querySelector('.second');
});

let secondElement2: HTMLElement | null = null;
$: scrollToSecond2 = () => {
  if (secondElement2) {
    secondElement2.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }
};

onMount(() => {
  secondElement2= document.querySelector('.scrol');
});
</script>
<div class="navbar bg-base-300">
    <div class="flex-1 px-2 lg:flex-none">
      <a class="text-lg font-bold">Nikola</a>
    </div>
    <div class="flex justify-end flex-1 px-2">
      <div class="flex items-stretch">
        <div class="dropdown dropdown-end">
          <label tabindex="0" class="btn btn-ghost rounded-btn">Menu</label>
          <ul tabindex="0" class="menu dropdown-content z-[1] p-2 shadow bg-base-100 rounded-box w-52 mt-4">
            <li><button on:click={()=>{goto("/welcome")}}><a>Projects</a></button></li> 
            <li><a on:click={scrollToSecond2}>About me</a></li>
            <li><a on:click={scrollToSecond}>Contact</a></li>
          </ul>
        </div>
      </div>
    </div>
  </div>
<div class="movie-container">
{#each data as d}
<div class="card w-96 bg-base-100 shadow-xl ml-24 mt-10">
  <figure><img src="{d.img}" alt="Shoes"/></figure>
  <div class="card-body">
    <h2 class="card-title">{d.fullName}</h2>
    <p>{d.description}</p>
    <div class="card-actions justify-end">
      <a href="{d.link}">
      <button class="btn btn-primary">Watch</button>
      </a>
    </div>
  </div>
</div>
{/each}
</div>
<div class="collapse bg-base-200">
  <input type="checkbox"/> 
  <div class="collapse-title text-xl font-medium">
    Skills and expertise
  </div>
  <div class="collapse-content"> 
  {#each skills as s}
  <div class="dropdown relative">
  <label tabindex="0" class="btn m-1">{s.name}</label>
  <div tabindex="0" class="dropdown-content z-[1] card card-compact w-64 p-2 shadow bg-neutral-focus text-primary-content">
    <div class="card-body">
      <h3 class="card-title">Progress</h3>
      <div class="mb-10">
        {s.name}  
        <div class="radial-progress" style="--value:{s.value};">{s.progress}</div>
    </div>
    </div>
  </div>
 </div>
{/each}
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
</div>
</div>
<div class="scrol">
<div class="collapse bg-base-200">
  <input type="checkbox" /> 
  <div class="collapse-title text-xl font-medium">
    About me!
  </div>
  <div class="collapse-content"> 
    <p>Hello! I am Nikola, a passionate and driven individual with
      a keen interest in technology and problem-solving.<br>
      My goal is to make a positive impact through innovative solutions and constant learning.</p>
  </div>
</div>
</div>
  <div class="second font-bold">You can contact me by:</div>
<div class="flex flex-col w-full lg:flex-row">
  <div class="grid flex-grow h-32 card bg-base-300 rounded-box place-items-center">Phone number: 067 401 360</div> 
  <div class="divider lg:divider-horizontal">OR</div> 
  <div class="grid flex-grow h-32 card bg-base-300 rounded-box place-items-center">Email adress: vnikolaa9@gmail.com</div>
</div>
<footer class="footer footer-center p-10 bg-base-200 text-base-content rounded">
  <div class="grid grid-flow-col gap-4">
    <a class="link link-hover">Personal Media</a> 
  </div> 
  <div>
    <div class="grid grid-flow-col gap-4">
      <a><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" class="fill-current"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"></path></svg></a> 
      <a><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" class="fill-current"><path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"></path></svg></a> 
      <a><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" class="fill-current"><path d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.192-1.333 1.115-1.333h2.885v-5h-3.808c-3.596 0-5.192 1.583-5.192 4.615v3.385z"></path></svg></a>
    </div>
  </div> 
</footer>
<style>
  .movie-container {
    display: flex;
    flex-wrap: wrap; 
    margin: -0.75rem; 
  }

  .card {
    margin: 0.75rem; 
  }
  .second {
    margin-top: 1000px; 
  }
  .scrol{

  }
</style> 
