<script>
    import { user } from "../../../stores/User";
    import { onMount } from "svelte";
    import { navigate } from "svelte-routing";
    import Navbar from "../global/Navbar.svelte";
    import FormEmpleados from "./FormEmpleados.svelte";

    onMount(() => {
        if (!$user) {
            navigate("/login", { replace: true });
        }
    });
</script>

<div>
    <Navbar />
    {#if $user}
        <h2>Empleados</h2>
        <FormEmpleados />
    {/if}
</div>