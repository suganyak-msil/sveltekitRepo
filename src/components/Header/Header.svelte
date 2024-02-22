<script>
  import { Router, Link, Route } from "svelte-navigator";
  import Home from "../../Pages/Home.svelte";
  import Help from "../../Pages/Help.svelte";
  import About from "../../Pages/About.svelte";
</script>

<Router>
  <div class="bg-blue-500 text-white p-4 flex  w-screen" >
    <div>
  <nav class="flex justify-between gap-4">
    <Link  to="/">Home</Link>
    <Link to="about">About</Link>
    <Link to="help">Help</Link>
  </nav>
</div>
</div>

  <div>
    <Route>
      <Route path="/">
        <Home />
      </Route>

      <Route path="/help">
        <Help />
      </Route>

      <Route path="/about">
        <About />
      </Route>
    </Route>
  </div>
</Router>
