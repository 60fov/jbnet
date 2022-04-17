<script lang='ts'>

  import { tweened } from "svelte/motion";
  import { sineOut } from "svelte/easing";

  let now_curr = 0;
  let now_data = [
    {
      title: "Korea",
      body: `
      i’m moving to Korea to learn the language and for the cultural experience.<br>
      why Korea? no particular reason; there are no travel restrictions [, for americans] and i did taekwondo as a kid so there’s a bit of familiarity.<br>
      how long? the original plan was to stay for 6 months, but we shall see... 
      `
    },
    {
      title: "skateboarding",
      body: `
      i skateboard, there's not much else to say about this.<br>
      a part one day though, fs.
      `
    },
    {
      title: "sewing",
      body: `
      designing and making clothes is fun + it reminds me of my late grandmother 🥰 (she was a seemstress).<br>
      im still super new, but definitely added the life repertoire.
      `
    },
  ];

  $: now = now_data[now_curr];

  const now_title = tweened("", {
    duration: 1000,
    easing: sineOut, // make typing easing function (noise?)
    interpolate: interpolateText
  });

  const now_body = tweened("", {
    duration: 2000,
    delay: 500,
    easing: sineOut,
    interpolate: interpolateText
  });

  $: $now_title = now.title;
  $: $now_body = now.body;

  function nowBubbleClick(event: MouseEvent) {
    const target = event.currentTarget as HTMLElement;
    now_curr = parseInt(target.getAttribute("data"));
  }

  function nowWheel(event: WheelEvent) {
    console.log("wheel");
    if (now_data[now_curr] != now || $now_title != now.title || $now_body != now.body) return;
    event.deltaX > +1 ? now_curr++ :
    event.deltaX < -1 ? now_curr-- :
    event.deltaY > +0 ? now_curr++ :
    event.deltaY < -0 ? now_curr-- : "";
    now_curr = wrap(now_curr, 0, now_data.length-1);
    console.log(now_curr);
    
  }

  function interpolateText(a: string, b: string) {
    return (t: number) => {
      // kinda cute ngl 💅
      let result = 
        t < 0.5 ?
        a.slice(0, a.length * (1-t*2)) : 
        b.slice(0, b.length * (t-0.5)*2);
      return result;
    }
  }

  function wrap(a: number, min: number, max: number) {
    a = 
      a > max ? min :
      a < min ? max :
      a;
    return a;
  }

</script>

<main>
  <header>
    <h1>jordan bailey</h1>
    <p>multidisciplinary autodidact</p>
  </header>

  <section id="works">
    <h3 class="section-label">works</h3>
    <ul class="works-list">
      <li class="work-item">
        <a class="work-name" target=_blank href="https://60fov.gitlab.io/krt/">krt<span class="work-desc">korean typing app</span></a>
      </li>
      <li class="work-item">
        <a class="work-name" target=_blank href="https://github.com/60fov/softsrv">softsrv<span class="work-desc">software renderer</span></a>
      </li>
      <li class="work-item">
        <a class="work-name" target=_blank href="https://www.urbandictionary.com/define.php?term=soon%20%28tm%29">0xGarden<span class="work-desc">blockchain garden</span></a>
      </li>
    </ul>
  </section>

  <section id="now">
    <span>
      <h3 class="section-label">now</h3>
      {#each now_data as now, i}
        <span
        data={`${i}`}
        class="now-bubble {i == now_curr ? `curr` : ``}"
        on:click={nowBubbleClick}
        ></span>
      {/each}
    </span>
    <div 
    class="now-part"
    on:wheel={nowWheel}>
      <h4 class="now-title"> {$now_title} </h4>
      <p class="now-desc"> {@html $now_body} </p>
    </div>
  </section>
  
</main>

<style lang='scss'>

  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  ul {
    list-style-type: none;
  }

   a {
     text-decoration: none;
     color: black;
   }

  main {
    margin: auto;
    width: clamp(250px, 80%, 500px);
    min-height: 100vh;
    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
    display: flex;
    flex-direction: column;
  }

  header {
    grid-area: 1 / 2 / 2 / 9;
    margin: 50px 0 0 0;

    h1 {
      text-transform: capitalize;
      font-size: clamp(1.5em, 9vw, 3em);
    }

    p {
      font-weight: 300;
      font-size: clamp(.6em, 3vw, 1em);
    }

  }

  section {
    display: flex;
    flex-direction: column;

    margin-top: 100px;

    .section-label {
      font-family: 'Times New Roman', Times, serif;
      font-style: italic;
      font-size: 1em;
      font-weight: normal;
      margin-bottom: 10px;
      display: inline-block;
    }
  }

  #works {
    grid-area: 3 / 3 / 4 / 5;
  }

  .works-list {
    display: flex;
    flex-direction: column;
    white-space: nowrap;

    .work-item {
      margin-bottom: 5px;
      font-size: 1.2em;

      .work-desc {
        margin-left: 5px;
        font-style: italic;
        font-size: .6em;
      }
    }
  }

  #now {
    grid-area: 3 / 6 / 5 / 8;

    
    .now-bubble {
      background-color: rgba(0, 0, 0, 0.25);
      width: .3em;
      height: .3em;
      border-radius: 100%;
      display: inline-block;
      margin-left: 10px;

      &.curr {
        background-color: black;
      }
    }
  }

  .now-part {
    display: flex;
    flex-direction: column;

    .now-title {
      font-weight: normal;
      font-size: 1.2em;
    }

    .now-desc {
      text-align: justify;
      letter-spacing: 1.5;
      line-height: 1.5;
      margin-bottom: 20px;
      word-break: break-word;
    }

  }

  @media screen and (min-width: 1024px) {
    main {
      width: 100vw;
      display: grid;
      grid-template-columns: repeat(9, 1fr);
      grid-template-rows: repeat(4, 1fr);
    }

    header {
      margin: 0 0 -1em 0;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
    }

    section {
      margin-top: -1em;
    }

    #works {
      grid-area: 3 / 3 / 5 / 5;
    }

  }
</style>