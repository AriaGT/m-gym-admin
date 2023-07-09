<script>
    import Navbar from "../global/Navbar.svelte";
    import FormProducts from "./FormProducts.svelte";
    import { user } from "../../../stores/User.js";
    import { onMount } from "svelte";
    import { navigate } from "svelte-routing";

    onMount(() => {
        if (!$user) {
            navigate("/login", { replace: true });
        }
    });
</script>

<div>
    <Navbar />
    {#if $user}
        <h2>Productos</h2>
        <FormProducts />
    {/if}
</div>
