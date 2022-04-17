<script lang='ts'>

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
    <h3 class="section-label">now</h3>
    <div class="now-part">
      <h4 class="now-title"> Korea </h4>
      <p class="now-desc">i’m moving to Korea to learn the language and for the cultural experience. why Korea? no particular reason; there are no travel restrictions [, for americans] and i did taekwondo as a kid so there’s a bit of familiarity. how long? the original plan was to stay for 6 months, but we shall see...</p>
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
      margin-bottom: -1em;

      h1 {
        align-self: flex-end;
      }

    }

    section {
      margin-top: -1em;
    }

    #works {
      grid-area: 3 / 3 / 5 / 5;
    }

  }
</style>