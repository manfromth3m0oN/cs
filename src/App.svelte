<script>
  import Nav from "./Nav.svelte";
  import { Router, Route } from "svelte-navigator";
  import Join from "./Join.svelte";
  import Create from "./Create.svelte";
  import Room from "./Room.svelte";
</script>

<Router>
  <header>
    <Nav />
  </header>
  <main>
    <Route path="/">
      <div class="center">
        <h1>Welcome to chanshare</h1>
        <p>Use the Links in the header to get around</p>
      </div>
    </Route>
    <Route path="join">
      <Join />
    </Route>
    <Route path="create">
      <Create />
    </Route>
    <Route path="about">
      <p>This is just an MVP see the full plans <a href="https://chanshare.github.io">here</a></p>
    </Route>
    <Route path="room/:name" let:params>
      <Room name={params.name} />
    </Route>
  </main>
</Router>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 500px;
    /* margin: 0 auto; */
	margin: 0;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  /*
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
	*/
  :global(.container) {
    height: 95vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  :global(.center) {
	display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
    width: 100vw;
    align-items: center;
  }
</style>
