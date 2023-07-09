<script>
    import { user } from "../../../stores/User";
    import { onMount } from "svelte";
    import { navigate } from "svelte-routing";
    import Navbar from "../global/Navbar.svelte";
    import FormDiarios from "./FormDiarios.svelte";

    onMount(() => {
        if (!$user) {
            navigate("/login", {
                replace: true,
            });
        }
    });
</script>

<div>
    <Navbar />
    {#if $user}
        <h2>Clientes Diarios</h2>
        <FormDiarios />
    {/if}
</div>
