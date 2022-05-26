<script>
  import TitleBar from "../components/TitleBar.svelte";
  import MainNavigator from "../components/MainNavigator.svelte";
  import DonationMap from "../components/DonationMap.svelte";
</script>

<div class="columns is-vcentered">
  <div class="column is-two-thirds">
    <TitleBar subTitle={"Map of Donation Locations"} title={"Donation Services Inc."}/>
  </div>
  <div class="column">
    <MainNavigator/>
  </div>
</div>

<DonationMap/>
