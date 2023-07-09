<script>
  import { Router, Link, Route } from "svelte-routing";
  import { user } from "./stores/User";
  import Login from "./lib/views/Login.svelte";
  import Home from "./lib/views/Home.svelte";
  import Empleados from "./lib/components/empleados/Empleados.svelte";
  import Miembros from "./lib/components/miembros/Miembros.svelte";
  import Diarios from "./lib/components/diarios/Diarios.svelte";
  import Productos from "./lib/components/productos/Productos.svelte";

  import { onMount } from "svelte";
  import { navigate } from "svelte-routing";

  onMount(() => {
    if (!$user) {
      navigate("/login", { replace: true });
    }
  });
</script>

<section>
  <h1>Master GYM</h1>
  <Router>
    {#if !$user}
      <Link to="/login">Login</Link>
    {/if}

    <Route path="/home">
      <Home />
    </Route>
    <Route path="/login">
      <Login />
    </Route>
    <Route path="/empleados">
      <Empleados />
    </Route>
    <Route path="/miembros">
      <Miembros />
    </Route>
    <Route path="/diarios">
      <Diarios />
    </Route>
    <Route path="/productos">
      <Productos />
    </Route>
  </Router>
</section>

<style>
  section {
    background-color: rgba(0, 0, 0, 0.5);
    width: 90%;
    height: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 20px;
    padding: 10px;
    border: 5px solid #535bf2;
    border-radius: 15px;
  }

  h1 {
    margin: 5px;
    width: 200px;
    display: flex;
  }
</style>
