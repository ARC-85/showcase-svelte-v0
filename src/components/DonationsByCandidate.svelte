<script>
    import Chart from 'svelte-frappe-charts';
    import {getContext, onMount} from "svelte";
    const donationService = getContext("DonationService");
  
    let totalByCandidate = {
      labels: [],
      datasets: [
        {
          values: []
        }
      ]
    }
  
    function populateByCandidate(donationList, candidates) {
      totalByCandidate.labels = [];
      candidates.forEach(candidate => {
        totalByCandidate.labels.push(`${candidate.lastName}, ${candidate.firstName}`)
        totalByCandidate.datasets[0].values.push(0);
      })
      candidates.forEach((candidate, i) => {
        donationList.forEach(donation => {
          if (donation.candidate._id == candidate._id) {
            totalByCandidate.datasets[0].values[i] += donation.amount;
          }
        });
      });
    }

    export async function refreshChart() {
    let donationList = await donationService.getDonations();
    let candidates = await donationService.getCandidates()
    populateByCandidate(donationList, candidates);
  }
  
    onMount(async () => {
      let donationList = await donationService.getDonations();
      let candidates = await donationService.getCandidates()
      populateByCandidate(donationList, candidates);
    });
  
  </script>
  
  <h1 class="title is-4">By Candidate</h1>
  <Chart data={totalByCandidate} type="bar"/>