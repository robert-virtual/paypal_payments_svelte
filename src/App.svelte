<script lang="ts">
  import { Link, Route, Router } from "svelte-navigator";
  import Account from "./lib/Account.svelte";
  import LoginRegister from "./lib/LoginRegister.svelte";
</script>

<Router>
  <nav>
    <Link to="login-register">Login/Register</Link>
    <Link to="account">Acount</Link>
  </nav>
  <Route path="/login-register">
    <LoginRegister />
  </Route>
  <Route path="/account">
    <Account />
  </Route>
</Router>
