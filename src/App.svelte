<script lang="ts">
  import piccy from "./assets/piccy.png";

</script>

<main
  class="
  flex flex-col gap-8
  mx-auto w-5/6 pb-10
  font-sans font-bold
  sm:w-2/3
  md:w-1/2 md:text-lg 
  lg:py-32 lg:flex-row lg:justify-center">

  <div class="
    flex flex-col h-fit pt-8
    lg:pt-0 lg:w-1/3 lg:top-32 lg:sticky">
      <img src={piccy} alt="me" 
        class="
        rounded-lg w-full aspect-[21/9] object-cover object-bottom
        lg:aspect-square lg:mb-4" />
      <div>
        <div class="ml-2 text-2xl space-y-2 hidden">
          <p> <a href="#works">works</a> </p>
          <p> <a href="#now">now</a> </p>
          <p> <a href="#socials">socials</a> </p>
          <p> <a href="#contact">contact</a> </p>
        </div>
      </div>
  </div>

  <div class="w-full space-y-9">
    <div class="space-y-8">
      <h1 class="text-3xl md:text-4xl">I'm Jordan Bailey 👋🏾</h1>
      <p> i code, design, teach, among other things. </p>
      <p> i am an advocate for accessible quality education for all.  </p>
      <p> i enjoy learning about various systems, e.g. engines, game mechanics, computer graphics. </p>
      <p> i play(ed) video games mostly movement shooters, e.g. quake, cs, apex. </p>
    </div>

    <div class="space-y-4">
      <h2 class="text-2xl md:text-3xl" id="works">works</h2>
      <p>things i've made:</p>
      <ul class="pb-4">
        <li> <a class="underline" href="http://60fov.gitlab.io/krt" target="_blank">KRT, korean typing app</a> </li>
        <li> <a class="underline" href="http://60fov.github.io/gbp" target="_blank">gbp, a very vanilla side-scroller</a> </li>
      </ul>
      <p>things i've written:</p>
      <ul>
        <li> <a class="underline" 
            href="https://ilybb4l.notion.site/Learning-Ethereum-d5731bfb802241b8a741c676203e078c" 
            target="_blank">Learning Ethereum</a>
        </li>
        <li> <a class="underline"
            href="https://ilybb4l.notion.site/L-Systems-5bd740a3341749aca0d756b95ff3adc2"
            target="_blank">L-Systems</a>
        </li>
        <li> <a class="underline"
            href="https://ilybb4l.notion.site/NFT-Perspective-8472f264a51b4d4a9e05db4cb5df7443"
            target="_target">NFT Perspective</a>
        </li>
      </ul>
    </div>

    <div class="space-y-4">
      <h2 class="text-2xl md:text-3xl" id="now">now</h2>
      <p>visiting korea.</p>
      <p>freelancing developer.</p>
      <p>designing and making clothes.</p>
    </div>

    <div class="space-y-4">
      <h2 class="text-2xl md:text-3xl" id="socials">socials</h2>
      <p class="space-x-2">
        <a class="underline" target="_blank" href="https://www.behance.net/jordanbailey12"> behance </a>
        <a class="underline" target="_blank" href="https://github.com/60fov"> github </a>
        <a class="underline" target="_blank" href="https://t.me/personalcontext"> telegram </a>
        <a class="underline" target="_blank" href="https://www.twitter.com/personalcontext"> twitter </a>
      </p>
    </div>

    <div class="space-y-4">
      <h2 class="text-2xl md:text-3xl" id="contact">contact</h2>
      <p>email is on my github. 👆🏾</p>
      <p>dms are open.</p>
    </div>
  </div>

</main>

<style lang="scss">
  :global(body) {
    background-color: gold;
    color: black;
  }

   ul {
     list-style: '✦ ';
     list-style-position: inside;
   }

</style>
