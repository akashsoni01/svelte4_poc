<script>
  import { Router, Route, Link } from "svelte-routing";
  import { fade } from "svelte/transition";
  import Home from "./routes/Home.svelte";
  import About from "./routes/About.svelte";
  import NotFound from "./routes/NotFound.svelte";
  import { writable } from "svelte/store";

  // This store holds the state of whether the transition is in progress
  const isTransitioning = writable(false);

  // Function to call when starting a transition
  function startTransition() {
    isTransitioning.set(true);
  }

  // Function to call when ended a transition
  function endTransition() {
    isTransitioning.set(false);
  }
</script>

<Router>
  <nav>
    <Link to="/" on:click={startTransition}>Home</Link>
    <Link to="/about" on:click={startTransition}>About</Link>
  </nav>
  <section>
    <Route
      path="/"
      component={Home}
      transition={fade}
      transitionState={isTransitioning}
      on:introend={endTransition}
      on:outrostart={startTransition}
      on:outroend={endTransition}
    />
    <Route
      path="/about"
      component={About}
      transition={fade}
      transitionState={isTransitioning}
      on:introend={endTransition}
      on:outrostart={startTransition}
      on:outroend={endTransition}
    />
    <Route
      path="*"
      component={NotFound}
      transition={fade}
      transitionState={isTransitioning}
      on:introend={endTransition}
      on:outrostart={startTransition}
      on:outroend={endTransition}
    />
  </section>
</Router>
