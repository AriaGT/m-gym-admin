<script>
    import { Link, navigate } from "svelte-routing";
    import { user } from "../../../stores/User.js";

    const cerrarSesion = () => {
        user.setUser(null);
        navigate("/login", { replace: true });
    };
</script>

<nav>
    {#if $user}
        <Link to="/home">Home</Link>
        <Link to="/empleados">Empleados</Link>
        <Link to="/miembros">Miembros</Link>
        <Link to="/diarios">Client Diarios</Link>
        <Link to="/productos">Productos</Link>

        <a on:click={cerrarSesion}>Cerrar Sessión</a>
    {/if}
</nav>

<style>
    nav {
        background-color: rgba(0, 0, 0, 0.5);
        border-radius: 15px;
    }

    nav {
        display: flex;
        justify-content: space-around;
        gap: 20px;
    }

    nav {
        padding: 5px;
        margin: 5px;
        text-transform: uppercase;
    }

    a {
        transition: transform 0.2s;
    }

    a:hover {
        color: red;
        font-size: bold;
        transform: scale(1.1);
        cursor: pointer;
    }

    @media (max-width: 768px) {
        nav {
            /* width: 70%; */
            display: flex;
            flex-direction: column;
        }
    }

</style>
