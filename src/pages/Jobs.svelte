<script>
import { onMount } from 'svelte';
import NewsList from '../components/NewsList.svelte';

let promise = getJobs();

async function getJobs() {
  const res = await fetch('https://api.hackernews.io/jobs');
  const jobsList = await res.json();
  return jobsList;
}
</script>


{#await promise}
  <p>loading...</p>
{:then jobsList}
  <NewsList list={jobsList} />
{/await}