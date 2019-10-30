<script>
import { onMount } from 'svelte';
import NewsList from '../components/NewsList.svelte';

let promise = getNewests();

async function getNewests() {
  const res = await fetch('https://api.hackernews.io/newest');
  const newestsList = await res.json();
  return newestsList;
}
</script>


{#await promise}
  <p>loading...</p>
{:then newestsList}
  <NewsList list={newestsList} />
{/await}