<script>
  import {setContext} from "svelte";
  import {DonationService} from "./services/donation-service";
  import Main from "./pages/Main.svelte"
  import Login from "./pages/Login.svelte"
  import Signup from "./pages/Signup.svelte"
  import Report from "./pages/Report.svelte";
  import Donate from "./pages/Donate.svelte";
  import Map from "./pages/Map.svelte";
  import Router from "svelte-spa-router";
  import Charts from "./pages/Charts.svelte";

  setContext("DonationService", new DonationService("http://localhost:4000"));

  let routes = {
    "/": Main,
    "/login": Login,
    "/signup": Signup,
    "/donate": Donate,
    "/report": Report,
    "/map": Map,
    "/charts": Charts,
    "/logout": Main
  }
</script>

<div class="container">
  <Router {routes}/>
</div>
