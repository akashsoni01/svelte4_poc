<script>
  import { Router, Route, Link } from "svelte-routing";
  import Home from "./routes/Home.svelte";
  import About from "./routes/About.svelte";
  import NotFound from "./routes/NotFound.svelte";
</script>

<Router>
  <nav>
    <Link to="/">Home</Link>
    <Link to="/about">About</Link>
  </nav>
  <section>
    <Route path="/" component={Home} />
    <Route path="/about" component={About} />
    <Route path="*" component={NotFound} />
  </section>
</Router>
