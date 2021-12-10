<script lang="ts">
  import { Router, Link, Route } from "svelte-routing";

  import Home from "./routes/Home.svelte";
  import About from "./routes/About.svelte";
  import BlogPost from "./routes/BlogPost.svelte";

  export let url = "";
</script>

<Router {url}>
  <nav>
    <Link to="/">Home</Link>
    <Link to="about">About</Link>
    <Link to="blog/1">Blog 1</Link>
    <Link to="blog/2">Blog 2</Link>
    <Link to="blog/3">Blog 3</Link>
    <Link to="blog/4?foo=bar">Blog with hash</Link>
  </nav>
  <div>
    <Route path="/">
      <Home />
    </Route>
    <Route path="about">
      <About />
    </Route>
    <Route path="blog/:id" let:params>
      <BlogPost id={params.id} />
    </Route>
  </div>
</Router>
