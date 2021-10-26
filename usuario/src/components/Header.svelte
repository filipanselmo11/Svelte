<script>
    import { Router, Link, Route } from "svelte-routing";
    import Home from "../views/Home.svelte";
    import Cadastro from "./Cadastro.svelte";
    import Login from "./Login.svelte";

    export let url = "";
</script>

<Router {url}>
    <nav class="navbar navbar-dark" style="background-color: #808080;">
        <a class="navbar-brand" href="/">App do Usuário</a>
        <div class="link">
            <a class="navbar-brand" style="color: #ffffff;" href="/"
                ><Link to="/">Home</Link></a
            >
            <a class="navbar-brand" style="color: #ffffff;" href="cadastro"
                ><Link to="cadastro">Cadastro</Link></a
            >
            <a class="navbar-brand" style="color: #ffffff;" href="login"
                ><Link to="login">Login</Link></a
            >
        </div>
    </nav>
    <div>
        <Route path="/"><Home /></Route>
        <Route path="cadastro" component={Cadastro} />
        <Route path="login" component={Login} />
    </div>
</Router>

<style>
    .link {
        color: #ffffff important;
    }
</style>
