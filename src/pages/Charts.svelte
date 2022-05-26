<script>
    import TitleBar from "../components/TitleBar.svelte";
    import MainNavigator from "../components/MainNavigator.svelte";
    import DonationsByCandidate from "../components/DonationsByCandidate.svelte";
    import DonationsByMethod from "../components/DonationsByMethod.svelte";
  </script>
  
  <div class="columns is-vcentered">
    <div class="column is-two-thirds">
      <TitleBar subTitle={"Donation Analytics"} title={"Donation Services Inc."}/>
    </div>
    <div class="column">
      <MainNavigator/>
    </div>
  </div>
  
  <div class="columns">
    <div class="column has-text-centered">
      <DonationsByMethod/>
    </div>
    <div class="column has-text-centered">
      <DonationsByCandidate/>
    </div>
  </div>