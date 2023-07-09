<script>
    import FormDates from "./FormMiembros.svelte";
    import { user } from "../../../stores/User.js";
    import { onMount } from "svelte";
    import { navigate } from "svelte-routing";
    import Navbar from "../global/Navbar.svelte";

    onMount(() => {
        if (!$user) {
            navigate("/login", { replace: true });
        }
    });
</script>

<div>
    <Navbar />
    {#if $user}
        <h2>Miembros</h2>
        <FormDates />
    {/if}
</div>
